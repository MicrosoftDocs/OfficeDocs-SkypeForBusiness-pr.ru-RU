---
title: Настройка сервера видеосвязи в Skype для бизнеса Server
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
description: Сводка. Настройка роли сервера видеосвязи (VIS) в Skype для бизнеса Server.
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820699"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Настройка сервера видеосвязи в Skype для бизнеса Server
 
**Сводка:** Настройте роль сервера video interop Server (VIS) в Skype для бизнеса Server.
  
 Настройте параметры, которые VIS будет связывать с видеомагольниками с помощью Windows PowerShell. После установки службы VIS создается конфигурация видеоманкетов с глобальной областью действия. Эта конфигурация видеомафигуры применяется VIS для всех магистральных магистрали, которые не имеют конфигурации видеомаголи с более конкретной областью действия. Обратите внимание, что конфигурация видеомайлов — это коллекция параметров, применимых к видеомагольникам.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Настройка видеомаголи и телефонной плана

Используйте следующие Windows PowerShell, чтобы указать конфигурацию видеомайлов и телефонную связь, которые должны быть связаны с новыми магистральными магистральми, определенными в документе топологии между VIS и всеми видео шлюзами. Все эти параметры можно установить на глобальном уровне, уровне сайта или службы (видео шлюза). 
  
Для каждого развертывания Skype для бизнеса Server создается dial plan с глобальной областью действия. Эта dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Настройка VIS с помощью Windows PowerShell

1. Создайте новую конфигурацию видеомагигании (коллекцию параметров) для использования в магистрали между VIS и Cisco Unified Communications Manager (CallManager или CUCM), используя следующий Windows PowerShell:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Если требуется изменить существующую видеомаголь, используйте следующий Windows PowerShell:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Чтобы просмотреть параметры, связанные с определенной конфигурацией видеоманкетов, используйте следующий Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Чтобы удалить определенную конфигурацию видеоманкстрали, используйте следующий Windows PowerShell (обратите внимание, что конфигурация видеомайлов с глобальной областью действия будет применяться, если для определенной магистрали нет более конкретной конфигурации видеоманкстрали):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Создайте dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое будет мешать ожидаемому взаимодействию VIS и CUCM.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) можно использовать для удаления телефонной программы.
  
Для видеовызова SIP-магистрали от видеошлюзов, URI запроса которого содержит номер, не отправляемый по номеру E.164, VIS считывает имя телефонной линии, связанной с связанной магистралью, и будет включать имя телефонной линии в контекстную часть URI запроса в приглашении, отправляемом VIS на передний план. Затем приложение перевода на переднем плане извлекает и применяет правила нормализации, связанные с этой телефонной линией, к URI запроса.
## <a name="trunk-configuration-options"></a>Параметры конфигурации магистрали

Указанные Windows PowerShell для конфигурации видеоманкетов были впервые в Skype для бизнеса Server 2015. Параметры, связанные с конфигурацией видеоманкетов, требуют краткого пояснения.
  
 **GatewaySendsRtcpForActiveCalls** Этот параметр определяет, отправляются ли пакеты RTCP из VTC в VIS для активных вызовов. В этом контексте активным вызовом является вызов, в котором разрешается передавать мультимедиа хотя бы в одном направлении. Если для GatewaySendsRtcpForActiveCalls задано true, VIS может завершить вызов, если он не получает пакеты RTCP в течение периода, превышающий 30 секунд. По умолчанию используется значение **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, будут ли пакеты RTCP по-прежнему перенаправлены по магистрали для вызовов, помещенных на удержание, и пакеты мультимедиа не будут поступать в любом направлении. ViS может завершить вызов, если пакеты RTCP, которые в настоящее время находятся на удержании, не перетекают из VTC в VIS. По умолчанию используется значение **True**. Если протокол SIPTransport имеет TCP, этот параметр игнорируется.
  
 **EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа, если для протокола SIPTransport задан протокол TLS. По умолчанию используется значение **True**. Если протокол SIPTransport имеет TCP, этот параметр игнорируется.
  
 **EnableSessionTimer** Этот параметр включает или отключает timers сеанса на стороне VIS для каждого диалоговое окно SIP, связанное с магистралью SIP видео. Значение по умолчанию - **false**.
  
 **ForwardErrorCorrectionType** Этот параметр используется для определения того, следует ли применять для видеопотоков прямое исправление ошибок (FEC) на этапе между сервером видеосвязи и видео шлюзом. Если параметр ForwardErrorCorrectionType имеет "None", FEC отключается между VIS и видео шлюзом/VTC. Установка параметра ForwardErrorCorrectionType в "Cisco" позволяет службе FEC совместимой с видео шлюзами Cisco, такими как Cisco Unified Communications Manager (CUCM). Значение по умолчанию **— None**.
  
## <a name="see-also"></a>См. также

[Настройка CUCM для связи со Skype для бизнеса Server](configure-cucm-for-interoperation.md)
