---
title: 'Lync Server 2013: Проверка наличия обновлений анализатора соответствия рекомендациям'
description: 'Lync Server 2013: Проверка наличия обновлений анализатора соответствия рекомендациям.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2662f143be9fc672461715d1c3da867886e686
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570975"
---
# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="4c09e-103">Проверка наличия обновлений анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c09e-103">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c09e-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4c09e-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4c09e-105">При запуске анализатора соответствия рекомендациям можно выполнить поиск последних обновлений для средства.</span><span class="sxs-lookup"><span data-stu-id="4c09e-105">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="4c09e-106">Если обновление доступно, вы можете скачать обновление.</span><span class="sxs-lookup"><span data-stu-id="4c09e-106">If an update is available, you can download the update.</span></span> <span data-ttu-id="4c09e-107">Если вы решили не загружать обновления или если анализатор соответствия рекомендациям не может получить доступ к Интернету, вы можете продолжать использовать версию, которая уже установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c09e-107">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c09e-108">Если для доступа к Интернету требуется проверка подлинности прокси-сервера, анализатор соответствия рекомендациям не может получить доступ к новым обновлениям, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="4c09e-108">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="4c09e-109">Тем не менее, вы можете вручную скачать последнюю версию RtcBPA.msi из центра загрузки Майкрософт по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A> .</span><span class="sxs-lookup"><span data-stu-id="4c09e-109">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="4c09e-110">После загрузки файла его можно скопировать на компьютер, на котором необходимо обновить анализатор соответствия рекомендациям, и использовать MSI файл для установки новой версии средства на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c09e-110">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="4c09e-111">Чтобы обновить правила анализатора соответствия рекомендациям, необходимо запустить средство от имени администратора на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c09e-111">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="4c09e-112">Если вы не вошли в систему с помощью учетной записи, которая является членом группы "Администраторы" и обнаружены обновления, закройте анализатор соответствия рекомендациям, а затем выполните следующую процедуру для запуска программы.</span><span class="sxs-lookup"><span data-stu-id="4c09e-112">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="4c09e-113">Чтобы открыть анализатор соответствия рекомендациям от имени администратора для проверки обновлений</span><span class="sxs-lookup"><span data-stu-id="4c09e-113">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="4c09e-114">На компьютере, на котором установлен анализатор соответствия рекомендациям, нажмите кнопку **Пуск**, выберите пункт **Microsoft Lync Server 2013**, щелкните правой кнопкой мыши **анализатор соответствия**рекомендациям, а затем выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="4c09e-114">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="4c09e-115">Укажите учетные данные для учетной записи, входящей в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="4c09e-115">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

