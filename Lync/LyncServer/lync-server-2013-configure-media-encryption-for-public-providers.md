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

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="2e6e8-102">Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e6e8-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e6e8-103">_**Последнее изменение темы:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="2e6e8-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="2e6e8-104">Если вы реализуете Федерацию аудио-и видеоданных (A/V) с помощью Windows Live Messenger, необходимо изменить два параметра: уровень шифрования Lync Server и политика свойство enablepubliccloudaccess.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="2e6e8-105">По умолчанию для уровня шифрования задано значение Required (Требуется).</span><span class="sxs-lookup"><span data-stu-id="2e6e8-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="2e6e8-106">Вам необходимо изменить это значение на Supported (Поддерживается).</span><span class="sxs-lookup"><span data-stu-id="2e6e8-106">You must change this setting to Supported.</span></span> <span data-ttu-id="2e6e8-107">Если параметр политики EnablePublicCloudAccess имеет значение false, то его необходимо изменить на **True**.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="2e6e8-108">Это можно сделать в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="2e6e8-109">Настройка федерации для Windows Live</span><span class="sxs-lookup"><span data-stu-id="2e6e8-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="2e6e8-110">Запустите командную консоль Lync Server на сервере переднего плана: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2e6e8-111">В командной строке введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="2e6e8-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="2e6e8-112">Этот шаг является обязательным, поскольку Windows Live Messenger не поддерживает шифрование видео и звука.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="2e6e8-113">Эта команда задает глобальную политику шифрования вместо требования шифрования видео и аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="2e6e8-114">Клиенты, поддерживающие шифрование, по-прежнему будут использовать шифрование, например Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2e6e8-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

