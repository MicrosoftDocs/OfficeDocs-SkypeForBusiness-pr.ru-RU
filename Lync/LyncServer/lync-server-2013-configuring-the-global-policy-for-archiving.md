---
title: 'Lync Server 2013: Настройка глобальной политики архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14cbb69ce620498e1d804483f97c47da37e8522
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="dd1cc-102">Настройка глобальной политики архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1cc-102">Configuring the global policy for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd1cc-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="dd1cc-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="dd1cc-104">При развертывании серверов переднего плана Lync Server создает глобальную политику для архивирования.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-104">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="dd1cc-105">По умолчанию архивация отключена в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-105">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="dd1cc-106">Глобальная политика определяет, включена ли архивация для внутренней и внешней связи для всего развертывания, если только вы не настроили политики сайта или пользователя, которые переопределят глобальную политику или используете Microsoft Exchange Integration для некоторых или всех ваших пользователей.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-106">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="dd1cc-107">Если вы используете Microsoft Exchange Integration, Глобальная политика не применяется ко всем пользователям, которые подключены к Exchange 2013, и почтовые ящики помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-107">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="dd1cc-108">Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, политики сайтов и пользователей, описаны [в разделе Архивация в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по планированию и документация по операциям.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd1cc-109">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="dd1cc-110">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="dd1cc-111">Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="dd1cc-112">Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="dd1cc-113">Настройка глобальной политики архивации при использовании баз данных для архивации в Lync Server</span><span class="sxs-lookup"><span data-stu-id="dd1cc-113">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="dd1cc-114">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dd1cc-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="dd1cc-116">Дополнительные сведения о различных способах запуска панели управления Lync Server 2013 можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dd1cc-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd1cc-117">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="dd1cc-118">На странице **Политика архивации** последовательно нажмите **Глобальная**, **Изменить** и **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-118">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dd1cc-119">На странице **Изменить политику архивации — глобальная** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-119">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="dd1cc-120">Если вы не хотите использовать имя "Глобальная" по умолчанию, укажите в поле **Имя** новое имя глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-120">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="dd1cc-121">В поле **Описание** укажите сведения о назначении этой политики (например, "Глобальная политика для *имя_подразделения*").</span><span class="sxs-lookup"><span data-stu-id="dd1cc-121">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="dd1cc-122">Для управления архивацией внутренних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-122">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="dd1cc-123">Для управления архивацией внешних коммуникаций для всех сайтов и пользователей, которые не управляются отдельными политиками на уровне сайта или пользователя, снимите или установите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-123">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="dd1cc-124">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="dd1cc-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

