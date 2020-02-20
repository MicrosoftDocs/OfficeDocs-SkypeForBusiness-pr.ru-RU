---
title: 'Lync Server 2013: Проверка наличия обновлений анализатора соответствия рекомендациям'
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
ms.openlocfilehash: 7850615a454541ee65dba310266b19b721ab185a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="ff295-102">Проверка наличия обновлений анализатора соответствия рекомендациям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff295-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff295-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ff295-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ff295-104">При запуске анализатора соответствия рекомендациям можно выполнить поиск последних обновлений для средства.</span><span class="sxs-lookup"><span data-stu-id="ff295-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="ff295-105">Если обновление доступно, вы можете скачать обновление.</span><span class="sxs-lookup"><span data-stu-id="ff295-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="ff295-106">Если вы решили не загружать обновления или если анализатор соответствия рекомендациям не может получить доступ к Интернету, вы можете продолжать использовать версию, которая уже установлена на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ff295-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff295-107">Если для доступа к Интернету требуется проверка подлинности прокси-сервера, анализатор соответствия рекомендациям не может получить доступ к новым обновлениям, которые можно скачать.</span><span class="sxs-lookup"><span data-stu-id="ff295-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="ff295-108">Тем не менее последнюю версию Рткбпа. msi можно скачать вручную в центре загрузки Майкрософт по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span><span class="sxs-lookup"><span data-stu-id="ff295-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="https://go.microsoft.com/fwlink/p/?linkid=266539">https://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="ff295-109">После загрузки файла его можно скопировать на компьютер, на котором необходимо обновить анализатор соответствия рекомендациям, и использовать MSI файл для установки новой версии средства на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="ff295-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="ff295-110">Чтобы обновить правила анализатора соответствия рекомендациям, необходимо запустить средство от имени администратора на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ff295-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="ff295-111">Если вы не вошли в систему с помощью учетной записи, которая является членом группы "Администраторы" и обнаружены обновления, закройте анализатор соответствия рекомендациям, а затем выполните следующую процедуру для запуска программы.</span><span class="sxs-lookup"><span data-stu-id="ff295-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="ff295-112">Чтобы открыть анализатор соответствия рекомендациям от имени администратора для проверки обновлений</span><span class="sxs-lookup"><span data-stu-id="ff295-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="ff295-113">На компьютере, на котором установлен анализатор соответствия рекомендациям, нажмите кнопку **Пуск**, выберите пункт **Microsoft Lync Server 2013**, щелкните правой кнопкой мыши **анализатор соответствия**рекомендациям, а затем выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="ff295-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="ff295-114">Укажите учетные данные для учетной записи, входящей в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="ff295-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

