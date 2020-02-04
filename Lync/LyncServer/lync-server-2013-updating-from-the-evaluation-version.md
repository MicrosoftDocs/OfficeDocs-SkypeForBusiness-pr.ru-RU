---
title: 'Lync Server 2013: обновление из ознакомительной версии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="27ecb-102">Обновление с ознакомительной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27ecb-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27ecb-103">_**Тема последнего изменения:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="27ecb-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="27ecb-104">Если вы установили ознакомительную версию Microsoft Lync Server 2013, вам, в конечном итоге, потребуется обновить установленную лицензионную копию программного обеспечения; Причина в том, что пробная версия истекает 180 дней после ее установки.</span><span class="sxs-lookup"><span data-stu-id="27ecb-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="27ecb-105">Однако вам не нужно полностью удалить ознакомительную версию, а затем установить лицензированную версию.</span><span class="sxs-lookup"><span data-stu-id="27ecb-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="27ecb-106">Вместо этого после получения действительного ключа лицензирования можно обновить ознакомительную версию Lync Server 2013, выполнив описанные ниже действия на каждом компьютере, который выступает в качестве сервера переднего плана Lync Server, режиссера или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="27ecb-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="27ecb-107">Обратите внимание, что вам не нужно обновлять компьютеры, выполняющие другие роли сервера, например сервер мониторинга или сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="27ecb-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="27ecb-108">Обновление ознакомительной версии Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27ecb-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="27ecb-109">Чтобы обновить на компьютере ознакомительную версию Lync Server 2013 до лицензированной версии программного обеспечения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="27ecb-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="27ecb-110">**Обновление ознакомительной версии Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="27ecb-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="27ecb-111">Войдите в систему под учетной записью локального администратора.</span><span class="sxs-lookup"><span data-stu-id="27ecb-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="27ecb-112">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="27ecb-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="27ecb-113">В командной консоли Lync Server введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="27ecb-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="27ecb-114">Обратите внимание, что вам может потребоваться указать полный путь к файлу файлового сервера. msi.</span><span class="sxs-lookup"><span data-stu-id="27ecb-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="27ecb-115">Этот файл можно найти в папке настройки установочных файлов в томе Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27ecb-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="27ecb-116">После завершения работы программы установки введите в командной строке следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="27ecb-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="27ecb-117">Повторите эту процедуру на любом другом сервере переднего плана, режиссере или пограничного сервера под управлением пробной копии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27ecb-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="27ecb-118">Эту процедуру также следует выполнять на всех серверах Office, которые были развернуты с помощью установочных файлов Lync Server Media.</span><span class="sxs-lookup"><span data-stu-id="27ecb-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="27ecb-119">Если вы не уверены в том, что пробная версия Lync Server запущена на данном компьютере, вы можете проверить ее, выполнив следующую команду в командной консоли Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="27ecb-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="27ecb-120">Командлет [Get-кссерверверсион](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) проанализирует локальный компьютер и сообщит один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="27ecb-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="27ecb-121">Что на компьютере установлен ключ корпоративного лицензирования Lync Server, и это означает, что обновление не требуется.</span><span class="sxs-lookup"><span data-stu-id="27ecb-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="27ecb-122">, Что ключ лицензии на ознакомительную версию Lync Server установлен, а это значит, что компьютер необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="27ecb-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="27ecb-123">На компьютере не требуется ключа корпоративного лицензирования.</span><span class="sxs-lookup"><span data-stu-id="27ecb-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="27ecb-124">Обновление ознакомительной версии до лицензионной версии требуется только на серверах переднего плана, режиссерах и пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="27ecb-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

