---
title: Использование анализатора соответствия рекомендациям для сканирования развертывания на наличие потенциальных проблем
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c3c2c5b49ae59c93ac6f78a2ae354061d7bf0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="3f570-102">Использование анализатора соответствия рекомендациям для сканирования развертывания Lync Server 2013 на наличие потенциальных проблем</span><span class="sxs-lookup"><span data-stu-id="3f570-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f570-103">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="3f570-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="3f570-104">Для выполнения сканирования с помощью анализатора соответствия рекомендациям необходимо задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3f570-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="3f570-105">**Учетные данные**   для запуска проверки необходимо войти на компьютер, на котором установлен анализатор соответствия рекомендациям, с помощью учетной записи, которая является членом локальной группы "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="3f570-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="3f570-106">Кроме того, нужно войти в систему с помощью пользовательской учетной записи, обладающей правами и разрешениями, необходимыми для выполнения соответствующих сканирований, либо при выполнении анализатора соответствия рекомендациям необходимо задать учетные данные, обладающие соответствующими правами и разрешениями пользователя.</span><span class="sxs-lookup"><span data-stu-id="3f570-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="3f570-107">Подробнее: сведения о [членстве в группах и требованиях пользователей для анализатора соответствия рекомендациям в Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="3f570-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="3f570-108">**Область сканирования**   чтобы указать область сканирования, выберите категории и серверы, которые нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="3f570-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="3f570-109">Вы можете выбрать все категории, одну или несколько категорий или один или несколько серверов в определенной категории в среде Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3f570-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="3f570-110">**Тип сканирования**   в настоящее время проверка работоспособности является единственным доступным типом проверки (выбрано по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3f570-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="3f570-111">Сканирование проверки работоспособности создает отчет, содержащий ошибки, предупреждения и другие сведения для всех серверов, определенных областью применения.</span><span class="sxs-lookup"><span data-stu-id="3f570-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="3f570-112">**Скорость сети параметры**   скорости включают быструю локальную сеть (100 Мбит/с и более), ЛВС (10 Мбит/с), Fast WAN (1,5 Мбит/с) или WAN (64 кбит/с).</span><span class="sxs-lookup"><span data-stu-id="3f570-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="3f570-113">Оценка времени выполнения сканирования основана на этом значении.</span><span class="sxs-lookup"><span data-stu-id="3f570-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="3f570-114">Это значение также используется для задания времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="3f570-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="3f570-115">В течение сканирования анализатор соответствия рекомендациям ожидает ответа сервера в течение заданного времени.</span><span class="sxs-lookup"><span data-stu-id="3f570-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="3f570-116">Если ответ не приходит в течение заданного времени ожидания, анализатор переходит к следующему серверу в сканировании.</span><span class="sxs-lookup"><span data-stu-id="3f570-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="3f570-117">Для медленных сетей это заданное время ожидание больше, чтобы учесть более длительные сетевые задержки.</span><span class="sxs-lookup"><span data-stu-id="3f570-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="3f570-118">Чтобы время ожидания анализатора не заканчивалось слишком быстро, рекомендуется выбирать для этого параметра значение, соответствующее самому медленному каналу в используемой топологии.</span><span class="sxs-lookup"><span data-stu-id="3f570-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="3f570-119">Сканирование развертывания Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f570-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="3f570-120">Войдите на компьютер, на котором установлен анализатор соответствия рекомендациям, используя учетную запись, входящую в локальную группу администраторов и обладающую другими необходимыми пользовательскими правами и разрешениями.</span><span class="sxs-lookup"><span data-stu-id="3f570-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="3f570-121">Нажмите кнопку **Пуск**, а затем последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **анализатор соответствия**рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="3f570-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="3f570-122">На экране **Добро пожаловать** щелкните **Выбор параметров нового сканирования**.</span><span class="sxs-lookup"><span data-stu-id="3f570-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="3f570-123">На странице **Подключиться к Active Directory** проверьте имя, указанное в поле **Сервер Active Directory**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3f570-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3f570-124">Чтобы выполнить сканирование, используя учетные данные, указанные при входе на компьютер, щелкните **Подключиться к серверу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3f570-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="3f570-125">Чтобы задать другие учетные данные, нужные для использования доменных служб Active Directory, пограничного сервера или сервера Exchange Server, щелкните **Показать дополнительные варианты входа**, установите все флажки, для которых необходимы отдельные учетные данные, задайте учетные данные для каждого установленного флажка, а затем щелкните **Подключиться к серверу Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3f570-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3f570-p105">Перед началом сканирования анализатор соответствия рекомендациям выполняет проверку сети и разрешений, чтобы гарантировать правильность указанных учетных данных и возможность подключения анализатора к доменным службам Active Directory. Если анализатор работает на сервере рабочей группы, он также проверяет возможность подключения к пограничным серверам в сети периметра (если они включены в сканирование).</span><span class="sxs-lookup"><span data-stu-id="3f570-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="3f570-128">На странице **Начать новое сканирование с проверкой соответствия рекомендациям** выберите варианты, которые нужно включить в сканирование, задайте скорость сети, а затем щелкните **Начать сканирование**.</span><span class="sxs-lookup"><span data-stu-id="3f570-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="3f570-129">На странице **Сканирование завершено** щелкните **Просмотреть отчет с рекомендациями для этого сканирования**.</span><span class="sxs-lookup"><span data-stu-id="3f570-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="3f570-130">На странице **Анализатор соответствия рекомендациям** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="3f570-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3f570-131">Чтобы просмотреть отчеты в списке, упорядочив их по серверному компоненту, щелкните view reports in a list organized by server component, click **Показать отчеты**, затем щелкните вкладку **Все вопросы** или **Информационные элементы**.</span><span class="sxs-lookup"><span data-stu-id="3f570-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="3f570-132">Чтобы просмотреть отчеты в иерархическом списке, упорядоченном по типам результатов, щелкните **Отчеты по дереву**, затем щелкните вкладку **Подробный отчет** или вкладку **Итоговый отчет**.</span><span class="sxs-lookup"><span data-stu-id="3f570-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="3f570-133">Чтобы просмотреть другие отчеты, щелкните **Другие отчеты**.</span><span class="sxs-lookup"><span data-stu-id="3f570-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3f570-134">Подробные сведения об отчетах анализатора соответствия рекомендациям и выявленных проблемах приведены в статье <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Просмотр и работа с отчетами, созданными анализатором соответствия рекомендациям в Lync server 2013</A> , а также <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">анализом и устранением проблем, определенных анализатором соответствия рекомендациям в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3f570-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

