---
title: Включение качества обслуживания для устройств без Windows
ms.reviewer: null
'ms:assetid': 26f793df-aef8-4028-9e3b-6c2c37ea61b9
'ms:mtpsurl': 'https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)'
'ms:contentKeyID': 48183661
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 'Узнайте, как включить QoS для устройств, используемых в организации, которые используют операционную систему, не Windows.'
---

# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Включение QoS в Skype для бизнеса Server для устройств, не основанных на Windows


При установке Skype для бизнеса Server, качество службы (QoS) не будет включено для устройств, используемых в организации, которые используют операционную систему, кроме Windows. Это можно проверить, заверив следующую команду из Skype для бизнеса ServerManagement Shell:

**Get-CsMediaConfiguration**

Если вы не внося изменений в параметры конфигурации мультимедиа, вам следует получить сведения, аналогичные этому:

Identity : Global<br/>
EnableQoS: False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Если свойство EnableQoS задается false (как и в предыдущем выпуске), это означает, что качество службы не включено для компьютеров и устройств, которые используют операционную систему, не Windows.

Чтобы включить качество службы в глобальном масштабе, запустите следующую команду из Skype для бизнеса Server командной Skype для бизнеса Server:

**Set-CsMediaConfiguration -EnableQoS $True**

Предшествуя команда включает QoS в глобальном масштабе; Однако важно отметить, что параметры конфигурации мультимедиа также могут применяться к области сайта. Если необходимо включить качество службы для сайта, необходимо включить удостоверение параметров конфигурации при вызове Set-CsMediaConfiguration. Например, эта команда включает QoS для сайта Redmond:

**Set-CsMediaConfiguration-Identity site:Redmond-EnableQoS $True**


> [!NOTE]
> Необходимо ли включить QoS в области сайта? Смотря как. Параметры области сайта имеют приоритет над настройками, назначенной глобальной области. Предположим, что QoS включен в глобальном масштабе, но отключен в области сайта (для сайта Redmond). В этом случае качество службы будет отключено для сайта Redmond; это потому, что параметры сайта имеют приоритет. Чтобы включить QoS для сайта Redmond, необходимо использовать параметры конфигурации мультимедиа, применяемые к этому сайту.


Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области), запустите эту команду из оболочки управления LSkype для бизнес-серверов:

**Get-CsMediaConfiguration | Set-CsMediaConfiguration EnableQoS $True**

Вы можете отключить QoS для устройств, которые используют операционную систему Windows, задав значение свойства EnableQoS false. Например:

**Set-CsMediaConfiguration-Identity site:Redmond-EnableQoS $False**

Таким образом вы можете включить качество обслуживания для отдельных частей сети (например, узла Redmond), не включая его для других частей.

QoS можно включить и отключить только с помощью Windows PowerShell. Эти параметры недоступны в панели Skype для бизнеса Server управления.

> [!NOTE]
> Skype для бизнеса для iOS Версии 6.17 и более поздней версии теперь поддерживают QoS.  Эта возможность QoS применима только к клиентам Skype для бизнеса и устройствам IP-телефонов, зарегистрированным непосредственно на внутреннем сервере Skype для бизнеса или Lync pool Server в управляемых сетях. QoS не применяется для трафика, пролегаемого через Интернет.
