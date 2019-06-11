---
title: 'Lync Server 2013: Проверка наличия обновлений анализатора соответствия рекомендациям'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a52aec0748bb5e96de0b3e6dafae4e05ddf9c15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="ec1b3-102">Проверка обновлений анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec1b3-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec1b3-103">_**Тема последнего изменения:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ec1b3-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ec1b3-104">Когда вы запускаете анализатор соответствия рекомендациям, с помощью этого средства вы можете найти последние обновления для этого средства.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="ec1b3-105">Если обновление доступно, вы можете скачать обновление.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="ec1b3-106">Если вы решили не загружать обновления или не можете получить доступ к Интернету, вы можете продолжать пользоваться версией, уже установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec1b3-107">Если для доступа к Интернету требуется проверка подлинности прокси-сервера, анализатору соответствия рекомендациям не удается получить доступ к новым обновлениям, которые вы хотите скачать.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="ec1b3-108">Тем не менее, вы можете вручную загрузить последнюю версию Рткбпа. msi из центра загрузки Майкрософт по адресу <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="ec1b3-109">После загрузки файла вы можете скопировать его на компьютер, на котором вы хотите обновить анализатор соответствия рекомендациям, и с помощью MSI-файла установить новую версию средства на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="ec1b3-110">Чтобы обновить правила анализатора соответствия рекомендациям, необходимо запустить средство в качестве администратора на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="ec1b3-111">Если вы не вошли в систему с помощью учетной записи, которая входит в группу администраторов, и обнаружены обновления, закройте анализатор соответствия рекомендациям, а затем выполните указанные ниже действия, чтобы запустить программу.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="ec1b3-112">Чтобы открыть анализатор соответствия рекомендациям в качестве администратора, чтобы проверить наличие обновлений, выполните описанные выше.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="ec1b3-113">На компьютере, на котором установлен анализатор соответствия рекомендациям, нажмите кнопку **Пуск**, выберите пункт **Microsoft Lync Server 2013**, щелкните правой кнопкой **анализатор соответствия рекомендациям**и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="ec1b3-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="ec1b3-114">Укажите учетные данные для учетной записи, которая входит в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="ec1b3-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

