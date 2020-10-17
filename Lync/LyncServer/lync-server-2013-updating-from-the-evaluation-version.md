---
title: 'Lync Server 2013: обновление из ознакомительной версии'
description: 'Lync Server 2013: обновление из ознакомительной версии.'
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
ms.openlocfilehash: 340badf9f5d2506c50cf8c03faa82223eabbd5af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546255"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="862c3-103">Обновление ознакомительной версии Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="862c3-103">Updating from the evaluation version of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="862c3-104">_**Последнее изменение темы:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="862c3-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="862c3-105">Если вы установили оценочную версию Microsoft Lync Server 2013, вам, в конечном итоге, потребуется обновить установленную лицензионную копию программного обеспечения; Это связано с тем, что срок действия ознакомительной версии истечет через 180 дней после ее установки.</span><span class="sxs-lookup"><span data-stu-id="862c3-105">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="862c3-106">Однако вам не нужно будет полностью удалять ознакомительную версию, а затем устанавливать лицензионную.</span><span class="sxs-lookup"><span data-stu-id="862c3-106">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="862c3-107">Вместо этого после получения действительного ключа лицензирования можно обновить оценочную версию Lync Server 2013, выполнив следующую процедуру на каждом компьютере, работающем в качестве сервера переднего плана Lync Server, директора или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="862c3-107">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="862c3-108">Обратите внимание на то, что вам не нужно обновлять компьютеры с другими ролями сервера, например сервера мониторинга или сервера архивации.</span><span class="sxs-lookup"><span data-stu-id="862c3-108">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="862c3-109">Обновление с ознакомительной версии Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="862c3-109">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="862c3-110">Чтобы обновить компьютер с ознакомительной версии Lync Server 2013 до лицензионной версии программного обеспечения, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="862c3-110">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="862c3-111">**Обновление с ознакомительной версии Microsoft Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="862c3-111">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="862c3-112">Войдите на компьютер как локальный администратор.</span><span class="sxs-lookup"><span data-stu-id="862c3-112">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="862c3-113">Нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="862c3-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="862c3-114">В командной консоли Lync Server введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="862c3-114">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="862c3-115">Обратите внимание на то, что вам может потребоваться указать полный путь к файлу server.msi.</span><span class="sxs-lookup"><span data-stu-id="862c3-115">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="862c3-116">Этот файл можно найти в папке Setup файла установки мультимедиа для тома Lync Server.</span><span class="sxs-lookup"><span data-stu-id="862c3-116">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="862c3-117">После завершения работы программы установки введите в командной строке следующую команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="862c3-117">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="862c3-118">Повторите эту процедуру для любого другого сервера переднего плана, директора или пограничного сервера под управлением пробной копии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="862c3-118">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="862c3-119">Эту процедуру также следует выполнить на всех серверах филиалов, развернутых с помощью файлов установки мультимедиа Lync Server.</span><span class="sxs-lookup"><span data-stu-id="862c3-119">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="862c3-120">Если вы не уверены в том, что пробная версия Lync Server запущена на определенном компьютере, можно проверить, выполнив следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="862c3-120">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="862c3-121">Командлет [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) проанализирует локальный компьютер и выдаст одно из следующих сообщений.</span><span class="sxs-lookup"><span data-stu-id="862c3-121">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="862c3-122">, Что на компьютере установлен ключ корпоративного лицензирования Lync Server, то есть обновление не требуется.</span><span class="sxs-lookup"><span data-stu-id="862c3-122">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="862c3-123">, Что установлен ключ лицензии на пробную версию Lync Server, то есть компьютер необходимо обновить.</span><span class="sxs-lookup"><span data-stu-id="862c3-123">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="862c3-p104">На компьютере не требуется ключ многократной установки. Обновление с ознакомительной версии до лицензионной требуется только на серверах переднего плана, Директорах и пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="862c3-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

