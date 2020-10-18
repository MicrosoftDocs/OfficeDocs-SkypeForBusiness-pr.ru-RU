---
title: 'Lync Server 2013: Настройка шифрования мультимедиа для общедоступных поставщиков'
description: 'Lync Server 2013: Настройка шифрования мультимедиа для общедоступных поставщиков.'
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
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577625"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="62589-103">Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62589-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62589-104">_**Последнее изменение темы:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="62589-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="62589-105">Если вы реализуете Федерацию аудио-и видеоданных (A/V) с помощью Windows Live Messenger, необходимо изменить два параметра: уровень шифрования Lync Server и политика свойство enablepubliccloudaccess.</span><span class="sxs-lookup"><span data-stu-id="62589-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="62589-106">По умолчанию для уровня шифрования задано значение Required (Требуется).</span><span class="sxs-lookup"><span data-stu-id="62589-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="62589-107">Вам необходимо изменить это значение на Supported (Поддерживается).</span><span class="sxs-lookup"><span data-stu-id="62589-107">You must change this setting to Supported.</span></span> <span data-ttu-id="62589-108">Если параметр политики EnablePublicCloudAccess имеет значение false, то его необходимо изменить на **True**.</span><span class="sxs-lookup"><span data-stu-id="62589-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="62589-109">Это можно сделать в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62589-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="62589-110">Настройка федерации для Windows Live</span><span class="sxs-lookup"><span data-stu-id="62589-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="62589-111">Запустите командную консоль Lync Server на сервере переднего плана: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="62589-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="62589-112">В командной строке введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="62589-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="62589-113">Этот шаг является обязательным, поскольку Windows Live Messenger не поддерживает шифрование видео и звука.</span><span class="sxs-lookup"><span data-stu-id="62589-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="62589-114">Эта команда задает глобальную политику шифрования вместо требования шифрования видео и аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="62589-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="62589-115">Клиенты, поддерживающие шифрование, по-прежнему будут использовать шифрование, например Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="62589-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

