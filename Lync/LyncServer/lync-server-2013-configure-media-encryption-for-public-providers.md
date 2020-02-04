---
title: 'Lync Server 2013: настройка шифрования мультимедиа для общедоступных поставщиков'
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
ms.openlocfilehash: 6d4ab36d19726a6092f978a2ac2a119b248cd0f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="5446c-102">Настройка шифрования мультимедиа для общедоступных поставщиков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5446c-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5446c-103">_**Тема последнего изменения:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="5446c-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="5446c-104">Если вы реализуете Федерацию аудио-и видеосвязи (A/V) с Windows Live Messenger, необходимо изменить два параметра: уровень шифрования Lync Server и политика Енаблепубликклаудакцесс.</span><span class="sxs-lookup"><span data-stu-id="5446c-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="5446c-105">По умолчанию задано значение "обязательный уровень шифрования".</span><span class="sxs-lookup"><span data-stu-id="5446c-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="5446c-106">Этот параметр необходимо изменить на "поддерживается".</span><span class="sxs-lookup"><span data-stu-id="5446c-106">You must change this setting to Supported.</span></span> <span data-ttu-id="5446c-107">Если для политики Енаблепубликклаудакцесс задано значение false, необходимо установить **значение true**.</span><span class="sxs-lookup"><span data-stu-id="5446c-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="5446c-108">Это можно сделать в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5446c-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="5446c-109">Настройка Федерации для Windows Live</span><span class="sxs-lookup"><span data-stu-id="5446c-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="5446c-110">Запустите командную консоль Lync Server на сервере переднего плана: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5446c-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5446c-111">В командной строке введите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="5446c-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="5446c-112">Это действие является обязательным, так как в Windows Live Messenger не поддерживается шифрование аудио-и видеофайлов.</span><span class="sxs-lookup"><span data-stu-id="5446c-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="5446c-113">В команде для глобальной политики задано значение параметра шифрование поддержки, а не необходимость шифрования аудио-и видеоданных.</span><span class="sxs-lookup"><span data-stu-id="5446c-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="5446c-114">Клиенты, которые поддерживают шифрование, по-прежнему будут использовать шифрование, например Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5446c-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

