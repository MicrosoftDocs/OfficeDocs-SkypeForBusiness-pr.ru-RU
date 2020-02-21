---
title: Создание и Настройка политик пользователей для архивации в Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f772119bac58f9ddd436289c8f1df210665d858d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="4c6fd-102">Создание и Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c6fd-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c6fd-103">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="4c6fd-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="4c6fd-104">Чтобы включить или отключить архивацию для отдельных пользователей, размещенных на Lync Server, необходимо сначала создать политику пользователя, а затем применить эту политику к одному или нескольким пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="4c6fd-105">Сведения о применении политик пользователей к определенным пользователям и группам пользователей приведены в статье [применение политики архивации Lync Server к пользователю в Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4c6fd-106">Сведения о том, как работают политики архивации, [2013 в](lync-server-2013-how-archiving-works.md) том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье по планированию, в документации по развертыванию или в документации по работе.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4c6fd-107">Если для развертывания включена интеграция с Microsoft Exchange, политики хранения на месте Exchange контролируют, включено ли архивирование для пользователей, размещенных в Exchange 2013 и почтовые ящики, которые помещаются на удержание на месте.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="4c6fd-108">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="4c6fd-109">Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="4c6fd-110">Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="4c6fd-111">Настройка политики архивации для пользователей, размещенных на сервере Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c6fd-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="4c6fd-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4c6fd-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="4c6fd-114">Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server 2013, можно найти в статье [Open the Lync server 2013 Tools администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4c6fd-115">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="4c6fd-116">Щелкните элемент **New** (Создать) и **User policy** (Политика пользователей).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="4c6fd-117">В окне **New Archiving Policy** (Новая политика архивации) выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4c6fd-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="4c6fd-118">В поле **Name** (Имя) укажите имя политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="4c6fd-119">В поле **Description** (Описание) укажите сведения о том, что из себя представляет данная политика пользователей (например, политика пользователей для юридического отдела).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="4c6fd-120">Чтобы контролировать архивацию внутренних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="4c6fd-121">Чтобы контролировать архивацию внешних коммуникаций в рамках политики пользователей, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="4c6fd-122">Щелкните элемент **Commit** (Исполнить).</span><span class="sxs-lookup"><span data-stu-id="4c6fd-122">Click **Commit**.</span></span>

<span data-ttu-id="4c6fd-123">Политика пользователей применяется только к тем пользователям, которым вы ее назначили.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="4c6fd-124">Сведения о применении политики пользователей к определенным пользователям приведены в статье [применение политики архивации Lync Server к пользователю в Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4c6fd-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

