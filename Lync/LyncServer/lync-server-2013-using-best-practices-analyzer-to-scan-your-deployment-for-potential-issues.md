---
title: Использование анализатора соответствия рекомендациям для проверки развертывания на наличие потенциальных проблем
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7d881ebc35a4f56207fedaa8533f0a3df3c7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="07b30-102">Использование анализатора соответствия рекомендациям для проверки развертывания Lync Server 2013 на наличие потенциальных проблем</span><span class="sxs-lookup"><span data-stu-id="07b30-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07b30-103">_**Тема последнего изменения:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="07b30-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="07b30-104">Чтобы запустить проверку анализатора соответствия рекомендациям, необходимо указать следующее:</span><span class="sxs-lookup"><span data-stu-id="07b30-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="07b30-105">**Учетные данные**   для запуска сканирования необходимо войти в систему на компьютере, на котором установлен анализатор соответствия рекомендациям, с помощью учетной записи, которая входит в локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="07b30-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="07b30-106">Кроме того, вы должны войти в систему с помощью учетной записи пользователя, у которой есть права и разрешения, необходимые для выполнения соответствующих проверок, или указать учетные данные с необходимыми правами и разрешениями пользователей при запуске анализатора соответствия рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="07b30-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="07b30-107">Подробные сведения можно найти [в разделе членство в группах и требования к правам пользователей для анализатора соответствия рекомендациям в Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="07b30-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="07b30-108">**Область сканирования**   . чтобы задать область сканирования, выберите категории и серверы, которые нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="07b30-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="07b30-109">Вы можете выбрать все категории, одну или несколько категорий или один или несколько серверов в определенной категории среды Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07b30-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="07b30-110">**Тип сканирования**   в настоящее время проверка работоспособности является единственным доступным типом проверки (выбрано по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="07b30-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="07b30-111">В ходе проверки работоспособности создается отчет, который содержит ошибки, предупреждения и другие сведения для всех серверов, указанных в области.</span><span class="sxs-lookup"><span data-stu-id="07b30-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="07b30-112">\*\*\*\* Сетевые параметры скорость включают в себя быстрое подключение к сети (100 Мбит/с), ЛВС (10 Мбит/с), быстрая Глобальная сеть (1,5 Мбит/с) или WAN (64 кбит/с).   </span><span class="sxs-lookup"><span data-stu-id="07b30-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="07b30-113">Предполагаемое время выполнения проверки зависит от этого параметра.</span><span class="sxs-lookup"><span data-stu-id="07b30-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="07b30-114">Этот параметр также используется для задания периода ожидания.</span><span class="sxs-lookup"><span data-stu-id="07b30-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="07b30-115">В ходе сканирования анализатор соответствия рекомендациям ожидает ответа от сервера в течение определенного времени.</span><span class="sxs-lookup"><span data-stu-id="07b30-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="07b30-116">Если он не получает ответ в течение указанного периода ожидания, он перемещается к следующему серверу в ходе сканирования.</span><span class="sxs-lookup"><span data-stu-id="07b30-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="07b30-117">В более медленных сетях этот тайм-аут выходит за более длинные сетевые задержки.</span><span class="sxs-lookup"><span data-stu-id="07b30-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="07b30-118">Мы рекомендуем вам выбрать наиболее медленную ссылку в топологии для этого параметра, чтобы это средство не выходило слишком быстро.</span><span class="sxs-lookup"><span data-stu-id="07b30-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="07b30-119">Проверка развертывания Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07b30-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="07b30-120">Войдите на компьютер, на котором установлен анализатор соответствия рекомендациям, с помощью учетной записи, которая входит в локальную группу администраторов, и у нее есть другие необходимые права и разрешения пользователей.</span><span class="sxs-lookup"><span data-stu-id="07b30-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="07b30-121">Нажмите кнопку **Пуск**, наведите указатель на пункт **все программы**, выберите **Microsoft Lync Server 2013**, а затем — **анализатор соответствия рекомендациям**.</span><span class="sxs-lookup"><span data-stu-id="07b30-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="07b30-122">На экране **приветствия** нажмите кнопку **выбрать параметры для нового сканирования**.</span><span class="sxs-lookup"><span data-stu-id="07b30-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="07b30-123">На странице **Подключение к Active Directory** проверьте имя, указанное на **сервере Active Directory**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="07b30-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="07b30-124">Чтобы выполнить сканирование с использованием учетных данных, которые использовались для входа на компьютер, нажмите кнопку **подключиться к серверу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="07b30-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="07b30-125">Чтобы указать другие учетные данные, которые вы хотите использовать для доменных служб Active Directory, пограничного сервера или Exchange Server, нажмите кнопку **Показать дополнительные параметры входа**, установите Каждый флажок, для которого требуются отдельные учетные данные, укажите учетные данные. для каждого выбранного флажка и нажмите кнопку **подключиться к серверу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="07b30-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="07b30-126">Перед началом сканирования анализатор соответствия рекомендациям выполняет проверку сети и разрешений, чтобы убедиться в правильности указанных учетных данных, а также в том, что анализатор соответствия рекомендациям может подключаться к доменным службам Active Directory.</span><span class="sxs-lookup"><span data-stu-id="07b30-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="07b30-127">Если средство запущено на сервере рабочей группы, оно также проверяет, может ли он подключаться к пограничным серверам в демилитаризованной зоне (если они включены в проверку).</span><span class="sxs-lookup"><span data-stu-id="07b30-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="07b30-128">На странице **Начало нового сканирования** с рекомендациями выберите параметры, которые вы хотите включить в сканер, укажите скорость сети и нажмите кнопку **начать сканирование**.</span><span class="sxs-lookup"><span data-stu-id="07b30-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="07b30-129">На странице **Сканирование завершено** нажмите кнопку **Просмотр отчета о том, как проверить эти**рекомендации.</span><span class="sxs-lookup"><span data-stu-id="07b30-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="07b30-130">На странице **отчета** советы и рекомендации выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="07b30-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="07b30-131">Чтобы просмотреть отчеты в списке, упорядоченном по серверному компоненту, щелкните **список отчетов**, а затем откройте вкладку **все проблемы** или вкладку **информационные элементы** .</span><span class="sxs-lookup"><span data-stu-id="07b30-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="07b30-132">Чтобы просмотреть отчеты в виде иерархического списка, упорядоченного по типам результатов, нажмите кнопку **отчеты**по дереву, а затем откройте вкладку **подробное представление** или **представление Сводка** .</span><span class="sxs-lookup"><span data-stu-id="07b30-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="07b30-133">Чтобы просмотреть другие отчеты, выберите пункт **другие отчеты**.</span><span class="sxs-lookup"><span data-stu-id="07b30-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="07b30-134">Подробные сведения об анализаторах соответствия рекомендациям и выявленных проблемах можно найти <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">в разделе Просмотр и работа с отчетами, созданными анализатором соответствия рекомендациям в Lync Server 2013</A> , а также <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">анализ и устранение проблем, определенных анализатором соответствия рекомендациям в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="07b30-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

