---
title: 'Lync Server 2013: Настройка шифрования мультимедиа для общедоступных поставщиков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1775a845c10797d145c7ee1ad5def3af729f4f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a>Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-12-12_

Если вы реализуете Федерацию аудио-и видеоданных (A/V) с помощью Windows Live Messenger, необходимо изменить два параметра: уровень шифрования Lync Server и политика свойство enablepubliccloudaccess. По умолчанию для уровня шифрования задано значение Required (Требуется). Вам необходимо изменить это значение на Supported (Поддерживается). Если параметр политики EnablePublicCloudAccess имеет значение false, то его необходимо изменить на **True**. Это можно сделать в командной консоли Lync Server.

<div>

## <a name="configure-federation-for-windows-live"></a>Настройка федерации для Windows Live

1.  Запустите командную консоль Lync Server на сервере переднего плана: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.

2.  В командной строке введите следующие команды:
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > Этот шаг является обязательным, поскольку Windows Live Messenger не поддерживает шифрование видео и звука. Эта команда задает глобальную политику шифрования вместо требования шифрования видео и аудиоданных. Клиенты, поддерживающие шифрование, по-прежнему будут использовать шифрование, например Lync 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

