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
ms.openlocfilehash: cb4385d219173ca33ae7120dcf3e9d75d4c65f14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="6d9a6-102">Создание и Настройка политик пользователей для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d9a6-102">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9a6-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="6d9a6-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="6d9a6-104">Чтобы включить или отключить архивацию для конкретных пользователей, размещенных на Lync Server, необходимо сначала создать политику пользователя, а затем применить ее к одному или нескольким пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-104">To enable or disable Archiving for specific users homed on Lync Server, you must first create a user policy and then apply the policy to one or more users or user groups.</span></span> <span data-ttu-id="6d9a6-105">Дополнительные сведения о применении политик пользователей к определенным пользователям и группам пользователей можно найти в разделе [применение политики архивации сервера Lync Server для пользователя на Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-105">For details about applying user policies to specific users and user groups, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6d9a6-106">Сведения о том, как работают политики архивации, в том числе иерархия для глобальных политик, сайтов и пользователей, описаны в разделе сведения [о том, как работает архивация в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по развертыванию или в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, in the Deployment documentation, or in the Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6d9a6-107">Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange 2013, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="6d9a6-108">Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="6d9a6-109">Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="6d9a6-110">Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-110">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a><span data-ttu-id="6d9a6-111">Настройка политики архивации для пользователей, которые находятся на сервере Lync Server</span><span class="sxs-lookup"><span data-stu-id="6d9a6-111">To configure an archiving policy for users homed on Lync Server</span></span>

1.  <span data-ttu-id="6d9a6-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6d9a6-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-113">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="6d9a6-114">Дополнительные сведения о различных способах запуска панели управления Lync Server 2013 можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a6-114">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6d9a6-115">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="6d9a6-116">Нажмите **Создать** и выберите **Политика пользователя**</span><span class="sxs-lookup"><span data-stu-id="6d9a6-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="6d9a6-117">В области **Создание новой политики архивации** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-117">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="6d9a6-118">В поле **Имя** укажите имя политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-118">In **Name**, specify the name for the user policy.</span></span>
    
      - <span data-ttu-id="6d9a6-119">В поле **Описание** укажите сведения о том, что из себя представляет данная политика пользователей (например, политика пользователей для юридического отдела).</span><span class="sxs-lookup"><span data-stu-id="6d9a6-119">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
      - <span data-ttu-id="6d9a6-120">Чтобы контролировать архивацию внутренних коммуникаций в рамках политики пользователей, установите или снимите флажок **Архивация внутренних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-120">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="6d9a6-121">Чтобы контролировать архивацию внешних коммуникаций в рамках политики пользователей, установите или снимите флажок **Архивация внешних взаимодействий**.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-121">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="6d9a6-122">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-122">Click **Commit**.</span></span>

<span data-ttu-id="6d9a6-123">Политика пользователей применяется только к тем пользователям, которым вы ее назначили.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-123">A user policy applies only to users to whom you assign the policy.</span></span> <span data-ttu-id="6d9a6-124">Дополнительные сведения о применении политики пользователей к определенным пользователям можно найти в разделе [применение политики архивации сервера Lync Server для пользователя на Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="6d9a6-124">For details about applying a user policy to specific users, see [Applying a Lync Server Archiving policy to a user in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

