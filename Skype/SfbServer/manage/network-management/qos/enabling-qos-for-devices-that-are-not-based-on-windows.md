---
title: Включение качества обслуживания для устройств без Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Узнайте, как включить QoS для устройств, используемых в вашей организации, которые используют операционную систему, не влияемую на Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814179"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Включение QoS в Skype для бизнеса Server для устройств, не основанных на Windows


При установке Skype для бизнеса Server качество обслуживания (QoS) не будет включено для устройств, используемых в организации, которые используют операционную систему, кроме Windows. Для этого в командной оболочке Skype для бизнеса ServerManagement можно использовать следующую команду:

    Get-CsMediaConfiguration

Если вы не влияли на параметры конфигурации мультимедиа, необходимо получить сведения, аналогичные этим:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Если для свойства EnableQoS задается false (как в предыдущем выходе), это означает, что качество обслуживания не включено для компьютеров и устройств, которые используют операционную систему, не включаемую в Windows.

Чтобы включить качество обслуживания на глобальном уровне, в командной оболочке Skype для бизнеса Server запустите следующую команду:

    Set-CsMediaConfiguration -EnableQoS $True

В предыдущей команде QoS включается в глобальной области; однако важно отметить, что параметры конфигурации мультимедиа также могут применяться к области сайта. Если необходимо включить качество обслуживания для сайта, при вызове set-CsMediaConfiguration необходимо включить удостоверение параметров конфигурации. Например, эта команда включает QoS для сайта Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Требуется ли включить QoS на уровне сайта? Смотря как. Параметры, присвоенные области сайта, имеют приоритет над настройками, присвоенным глобальной области. Предположим, что qoS включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond). В этом случае качество обслуживания для сайта Redmond будет отключено; это потому, что приоритет имеют параметры сайта. Чтобы включить QoS для сайта Redmond, необходимо использовать параметры конфигурации мультимедиа, примененные к этому сайту.


Чтобы одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области действия), запустите эту команду в командной оболочке LSkype для бизнеса Server:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Вы можете отключить QoS для устройств, которые используют операционную систему, не включаемую в Windows, установив для свойства EnableQoS значение False. Пример:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Таким образом вы можете включить качество обслуживания для отдельных частей сети (например, узла Redmond), не включая его для других частей.

QoS можно включить и отключить только с помощью Windows PowerShell. Эти параметры недоступны в панели управления Skype для бизнеса Server.

> [!NOTE]
> Клиенты Skype для бизнеса для iOS версии 6.17 и более поздних версий теперь поддерживают QoS.  Эта возможность QoS применима только к клиентам Skype для бизнеса и устройствам IP-телефонов, которые зарегистрированы непосредственно на внутреннем сервере Skype для бизнеса или сервере пула Lync в управляемых сетях. QoS не применимо к трафику, маршрутуемого через Интернет.



