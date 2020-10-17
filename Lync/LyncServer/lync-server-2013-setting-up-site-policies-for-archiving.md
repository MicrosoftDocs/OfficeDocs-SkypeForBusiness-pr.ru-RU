---
title: 'Lync Server 2013: Настройка политик сайта для архивации'
description: 'Lync Server 2013: Настройка политик сайта для архивации.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558395"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="75168-103">Настройка политик сайта для архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75168-103">Setting up site policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75168-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="75168-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="75168-105">Архивацию можно включить или отключить для определенных сайтов, создав или настроив политику архивации для каждого из них.</span><span class="sxs-lookup"><span data-stu-id="75168-105">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="75168-106">Политика сайта переопределяет глобальную политику, а политики пользователей — политики сайта.</span><span class="sxs-lookup"><span data-stu-id="75168-106">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="75168-107">Политики архивации применяются только в том случае, если вы не используете интеграцию с Microsoft Exchange или если вы используете интеграцию Microsoft Exchange, но у вас есть некоторые пользователи, которые не размещены в Exchange 2013 и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="75168-107">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="75168-108">Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье Планирование [работы архивации в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по развертыванию или документация по операциям.</span><span class="sxs-lookup"><span data-stu-id="75168-108">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75168-109">Если для развертывания включена интеграция с Microsoft Exchange, политики хранения Exchange In-Place контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="75168-109">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="75168-110">Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75168-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="75168-111">Чтобы включить архивацию внутренних и внешних коммуникаций в политиках архивации, вы должны указать все соответствующие параметры конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="75168-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="75168-112">Дополнительные сведения приведены в статье <A href="lync-server-2013-configuring-archiving-options.md">Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75168-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="75168-113">Создание политики архивации для сайта</span><span class="sxs-lookup"><span data-stu-id="75168-113">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="75168-114">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="75168-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="75168-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75168-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="75168-116">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="75168-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="75168-117">Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, приведены в статье Планирование [работы архивации в среде Lync Server 2013](lync-server-2013-how-archiving-works.md) , документация по развертыванию или документация по операциям.</span><span class="sxs-lookup"><span data-stu-id="75168-117">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="75168-118">Нажмите кнопку **Создать** и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="75168-118">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="75168-119">В поле **Выбор сайта** щелкните сайт, к которому требуется применить политику.</span><span class="sxs-lookup"><span data-stu-id="75168-119">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="75168-120">В области **Создать политику архивации** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75168-120">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="75168-121">В поле **Имя** укажите имя для политики сайта.</span><span class="sxs-lookup"><span data-stu-id="75168-121">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="75168-122">В поле **Описание** укажите сведения о назначении политики сайта (например, "политика сайта для Москвы").</span><span class="sxs-lookup"><span data-stu-id="75168-122">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="75168-123">Чтобы выбрать управление архивацией внутренних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внутренних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="75168-123">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="75168-124">Чтобы выбрать управление архивацией внешних коммуникаций для указанного сайта, установите или снимите флажок **Архивация внешних коммуникаций**.</span><span class="sxs-lookup"><span data-stu-id="75168-124">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="75168-125">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="75168-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

