---
title: Настройка VIS в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Сводка: Настройка ролей сервера взаимодействия видео (VIS) в Скайп для Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a>Настройка VIS в Skype для бизнеса Server 2015
 
**Сводка:** Настройка ролей сервера взаимодействия видео (VIS) в Скайп для Business Server 2015.
  
 Настройте параметры, которые VIS будет связать с видео магистральных линий связи, с помощью Windows PowerShell. Конфигурация видеомагистралей с глобальной областью действия создается после установки службы VIS. Эта конфигурация видеомагистралей посредством VIS применяется ко всем магистралям, для которых не задана конфигурация видеомагистралей с более узкой областью действия. Следует учитывать, что конфигурация видеомагистралей представляет собой набор параметров, применимых к видеомагистралям.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Настройка видеомагистрали и абонентской группы

Используйте следующие команды Windows PowerShell, чтобы указать Настройка видео линии связи и абонентская группа планирования должен быть связан с недавно определенной trunk(s), определенным в документе топологии между VIS и все шлюзы видео. Все эти параметры могут быть заданы на глобальном уровне, уровне сайта или уровне службы (видеошлюза). 
  
Для развертывания сервера Business каждого Скайп создается абонентской группы с глобальной областью действия. Эта абонентская группа посредством VIS применяется ко всем магистралям, для которых не задана абонентская группа с более узкой областью действия. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Настройка VIS, с помощью Windows PowerShell

1. Создание новой конфигурации магистрали видео (набор параметров) для использования на линии связи между VIS и CUCM, с помощью следующего командлета Windows PowerShell:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Если имеется существующий видео линии связи, который необходимо изменить, используйте следующий командлет Windows PowerShell:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Чтобы просмотреть параметры, связанные с настройкой конкретной линии видео, используйте следующий командлет Windows PowerShell:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Чтобы удалить конфигурацию конкретной линии видео, используйте следующий командлет Windows PowerShell (Обратите внимание на то, что конфигурация магистрали с глобальной областью видео будет использоваться, если не более конкретно с областью видео магистральной конфигурации для конкретной линии):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Создание абонентской следует связать с магистралью, с помощью следующих командлетов Windows PowerShell:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

Команда **Remove-CsVoiceNormalizationRule** необходима для переопределения правила по умолчанию, которое нарушало бы ожидаемое взаимодействие между VIS и CUCM.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) используется для удаления абонентской группы.
  
Для SIP-магистрали видеозвонка от видео шлюза, чей URI запроса содержит номер не E.164 будет считывать имя абонентской, связанные с сопоставленном VIS, а в контексте телефона часть URI запроса в приглашении, VI будут включены имя абонентской группы S отправляет на сервере переднего плана. Затем в приложении трансляции на сервере переднего плана извлекаются связанные с абонентской группой правила нормализации для их применения к идентификатору URI запроса.
## <a name="trunk-configuration-options"></a>Варианты конфигурации магистралей

Командлеты Windows PowerShell для настройки видео магистрали, указанным выше появились в Скайп для Business Server 2015. Параметры, связанные с конфигурацией видеомагистрали, требуют краткого пояснения.
  
 **GatewaySendsRtcpForActiveCalls** Этот параметр определяет ли RTCP пакеты, отправляются из VTC VIS для активных звонков. В данном контексте активным считается вызов, для которого хотя бы в одном направлении разрешен поток мультимедийных данных. Если для параметра GatewaySendsRtcpForActiveCalls задано значение True, а на VIS в течение периода, превышающего 30 секунд, не принят ни один пакет RTCP, вызов завершается. По умолчанию задано значение **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Этот параметр определяет, пакеты RTCP продолжить передаваемых по линии связи для вызовов, которые были размещены на удержание и не пакетов мультимедиа должны проходить в обоих направлениях. Если в режиме удержания вызова поток пакетов RTCP из VTC на VIS отсутствует, вызов может быть завершен средствами VIS. По умолчанию задано значение **True**. Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.
  
 **EnableMediaEncryptionForSipOverTls** Этот параметр включает или отключает SRTP для мультимедиа, если протокол SIPTransport задано значение TLS. По умолчанию задано значение **True**. Этот параметр игнорируется, если в качестве транспортного протокола SIP задан протокол TCP.
  
 **EnableSessionTimer** Этот параметр включает или отключает таймеры сеанса на стороне VIS для каждого диалогового окна SIP, связанный с видео канала SIP. По умолчанию задано значение **False**.
  
 **ForwardErrorCorrectionType** Этот параметр используется для определения переадресовывать ошибка коррекции (FEC) для потоковое видео для применения на ветвь между сервером видео взаимодействия и видео шлюза. Параметр ForwardErrorCorrectionType значение «None» отключает FEC между VIS и видео шлюза/VTC. Установка ForwardErrorCorrectionType для «Cisco» позволяет FEC, совместимый с видео шлюзы, Cisco, таких как Cisco объединенных коммуникаций Manager (CUCM). По умолчанию задано значение **Нет**.
  
## <a name="see-also"></a>См. также

#### 

[Настройка CUCM для взаимодействия с Скайп для Business Server 2015](configure-cucm-for-interoperation.md)

