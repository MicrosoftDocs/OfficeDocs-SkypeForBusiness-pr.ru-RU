---
title: Включение качества обслуживания для устройств без Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Узнайте, как включить качество обслуживания для устройств, используемых в вашей организации, использующие операционной системы, отличных от Windows.
ms.openlocfilehash: 24d27b25112ecc982a6fdc2b8d1874c4be992937
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913058"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Включение качества обслуживания в Скайп для Business Server для устройств, не входящий в систему Windows


При установке Скайп для Business Server качества обслуживания (QoS) не быть включен для любого устройств, используемых в вашей организации, использующие операционной системы, отличных от Windows. Вы можете проверить, выполнив следующую команду в Скайп оболочки ServerManagement бизнеса:

    Get-CsMediaConfiguration

Если предположить, что вы не вносили изменений в параметры конфигурации мультимедиа, вы должны получить сведения, похожие на следующие:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Если свойство EnableQoS установлено значение False (как и в предыдущем вывод), это означает, что не включено качества обслуживания для компьютеров и устройств, использующих операционной системы, отличных от Windows.

Чтобы включить качество обслуживания на глобальном уровне, выполните следующую команду в Скайп для консоли Business Server:

    Set-CsMediaConfiguration -EnableQoS $True

Приведенная выше команда включает качества обслуживания на глобальном уровне; Тем не менее важно Обратите внимание на то, что параметры конфигурации мультимедиа можно также применяются на уровне сайта. Если требуется включить качество обслуживания для сайта, необходимо включить Identity параметров конфигурации при вызове Set-CsMediaConfiguration. Например эта команда включает качества обслуживания для сайта Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> Необходимо включить качество обслуживания на уровне сайта? Смотря как. Параметры, назначенные на уровне сайта имеют приоритет перед параметрами назначен на глобальном уровне. Предположим, что у вас есть QoS включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond). В этом случае будут отключены качества обслуживания для сайта Redmond; Вот так, как параметры сайта, имеют приоритет. Включение качества обслуживания для сайта Redmond, будет иметь для этого с помощью параметров конфигурации мультимедиа применяется для этого сайта.


Если вы хотите включить качество обслуживания одновременно для всех мультимедиа параметров конфигурации (вне зависимости от области действия), выполните следующую команду из внутри LSkype для консоли Business Server.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Можно отключить качества обслуживания для устройств, использующих операционной системы, отличных от Windows, задав значение свойства EnableQoS значение False. Например:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Это дает возможность реализации качества обслуживания на некоторые части сети (например, на сайте Redmond) при этом качества обслуживания на других частей сети отключена.

Только QoS могут включаться и отключаться с помощью Windows PowerShell. Эти параметры недоступны в Скайп для панели управления Business Server.


