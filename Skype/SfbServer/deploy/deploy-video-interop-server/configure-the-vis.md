---
title: Настройка сервера межоператоров видеосвязи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: Сводка. Настройка роли Video Interop Server (VIS) в Skype для бизнеса Server.
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120308"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Настройка сервера межоператоров видеосвязи в Skype для бизнеса Server
 
**Сводка:** Настройка роли Video Interop Server (VIS) в Skype для бизнеса Server.
  
 Настройка параметров, которые VIS будет связывать с магистральми видео с помощью Windows PowerShell. Конфигурация магистрали видео с глобальной областью создается после установки службы VIS. Эта конфигурация магистрали видео применяется VIS для всех магистральных магистрали, которые не имеют конфигурации магистрали видео с более определенной областью. Обратите внимание, что конфигурация магистрали видео — это коллекция параметров, применимых к магистральм видео.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Настройка магистрали видео и набора номера

Используйте следующие команды Windows PowerShell, чтобы указать конфигурацию магистрали видео и план набора номера, которые будут связаны с недавно определенным магистральом(ы), определенным в документе топологии между VIS и всеми шлюзами видео. Все эти параметры можно установить на уровнях Global, Site или Service (Video Gateway). 
  
Для развертывания Skype для бизнеса Server создается наборная программа с глобальной областью. Эта шкала применяется VIS для всех магистральных телефонов, у которых нет какой-либо телефонной программы с более определенной областью. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Настройка VIS с помощью Windows PowerShell

1. Создайте новую конфигурацию магистрали видео (набор параметров), которая будет использовать в магистрали между диспетчером единой связи VIS и Cisco (CallManager или CUCM), используя следующий Windows PowerShell:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Если имеется существующий магистраль видео, который необходимо изменить, используйте следующий Windows PowerShell.
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Чтобы просмотреть параметры, связанные с определенной конфигурацией магистрали видео, используйте следующий Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Чтобы удалить определенную конфигурацию магистрали видео, используйте следующий Windows PowerShell (обратите внимание, что глобально масштабная конфигурация магистрали видео будет применяться, если не существует более конкретной конфигурации магистрали видео для определенного магистраля):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Создайте план набора для связи с магистралью, используя следующие Windows PowerShell:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое будет мешать ожидаемому взаимодействию VIS и CUCM.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) можно использовать для удаления набора номера.
  
Для вызова магистрали видео SIP из видео шлюза, у которого URI запроса содержит номер, не связанный с E.164, VIS будет читать имя плана набора, связанного с связанным магистралью, и будет включать имя плана набора в контекстной части телефона URI запроса в приглашении, которое VIS отправляет в переднюю часть. Приложение для перевода на переднем конце извлекает и применяет правила нормализации, связанные с телефонной линией, к URI запроса.
## <a name="trunk-configuration-options"></a>Параметры конфигурации магистрали

Эти Windows PowerShell для конфигурации магистрали видео, упомянутые ранее, были новыми для Skype для бизнеса Server 2015. Параметры, связанные с конфигурацией магистрали видео, требуют краткого объяснения.
  
 **GatewaySendsRtcpForActiveCalls** Этот параметр определяет, отправляются ли пакеты RTCP из ВТС в VIS для активных вызовов. В этом контексте активным вызовом является вызов, в котором разрешается передавать мультимедиа хотя бы в одном направлении. Если в GatewaySendsRtcpForActiveCalls установлено true, VIS может прекратить вызов, если он не получает пакеты RTCP в течение более 30 секунд. По умолчанию используется значение **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, будут ли пакеты RTCP по-прежнему отправлены по магистрали для вызовов, которые были помещены на удержание, и не ожидается, что пакеты мультимедиа будут поступать в любом направлении. VIS может прекратить вызов, если пакеты RTCP не будут поступать из ВТС в VIS во время удержания вызова. По умолчанию используется значение **True**. Если протокол SIPTransport заданной для TCP, этот параметр игнорируется.
  
 **EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа при задании протокола SIPTransport к TLS. По умолчанию используется значение **True**. Если протокол SIPTransport заданной для TCP, этот параметр игнорируется.
  
 **EnableSessionTimer** Этот параметр включает или отключает время сеанса на стороне VIS для каждого диалоговика SIP, связанного с магистралью SIP видео. Значение по умолчанию - **false**.
  
 **ForwardErrorCorrectionType** Этот параметр используется для определения того, следует ли применять исправление ошибок вперед (FEC) для видеопотоков на ноге между сервером видеосвязи и шлюзом видео. Настройка ForwardErrorCorrectionType на "Нет" отключит FEC между VIS и видео шлюзом/VTC. Настройка ForwardErrorCorrectionType в "Cisco" позволяет FEC совместим с видео шлюзами Cisco, такими как Cisco Unified Communications Manager (CUCM). По умолчанию **нет**.
  
## <a name="see-also"></a>См. также

[Настройка CUCM для межоперации с помощью Skype для бизнеса Server](configure-cucm-for-interoperation.md)