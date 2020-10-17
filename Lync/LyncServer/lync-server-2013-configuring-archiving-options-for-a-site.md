---
title: 'Lync Server 2013: Настройка параметров архивации для сайта'
description: 'Lync Server 2013: Настройка параметров архивации для сайта.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db164d7c4c1cdda158387be62c0eb535fac662f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562565"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="22a17-103">Настройка параметров архивации для сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22a17-103">Configuring Archiving options for a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a17-104">_**Последнее изменение темы:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="22a17-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="22a17-p101">Чтобы задать параметры архивации, которые должны применяться к определенным сайтам, создайте и настройте параметры в конфигурации архивации для каждого из этих сайтов. Конфигурация сайта переопределяет глобальную конфигурацию, но только для сайта, указанного в конфигурации. Конфигурации пулов переопределяют конфигурации сайтов.</span><span class="sxs-lookup"><span data-stu-id="22a17-p101">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites. A site configuration overrides the global configuration, but only for the site specified in the site configuration. Pool configurations override site configurations</span></span>

<span data-ttu-id="22a17-108">Сведения о том, как работает Настройка архивации, в том числе иерархия для конфигураций глобальных, сайтов и пулов, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="22a17-108">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22a17-109">Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="22a17-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="22a17-110">Чтобы включить архивацию, необходимо указать политики архивации для управления архивацией внутренних и внешних коммуникаций на глобальном уровне и (при необходимости) на уровне сайта и пользователя.</span><span class="sxs-lookup"><span data-stu-id="22a17-110">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="22a17-111">Если вы настраиваете политики на уровне пользователей, необходимо также назначить политики пользователей определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="22a17-111">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="22a17-112">Подробные сведения о создании и настройке политик архивации можно найти в статье <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="22a17-112">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="22a17-113">Настройка параметров архивации на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="22a17-113">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="22a17-114">Используя учетную запись пользователя, назначенную роли CsArchivingAdministrator или CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="22a17-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22a17-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22a17-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="22a17-116">Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server 2013, можно найти в статье [Open the Lync server 2013 Tools администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22a17-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22a17-117">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="22a17-117">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="22a17-118">На странице **Конфигурация архивации** щелкните **Создать** и затем выберите пункт **Конфигурация сайта**.</span><span class="sxs-lookup"><span data-stu-id="22a17-118">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="22a17-119">В разделе **Выбор сайта** выберите сайт, для которого нужно настроить архивацию.</span><span class="sxs-lookup"><span data-stu-id="22a17-119">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="22a17-120">На странице **Новый параметр архивации** в раскрывающемся списке **Параметр архивации** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="22a17-120">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="22a17-121">Чтобы включить архивацию только для сеансов обмена мгновенными сообщениями, выберите пункт **Архивировать сеансы обмена мгновенными сообщениями**.</span><span class="sxs-lookup"><span data-stu-id="22a17-121">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="22a17-122">Чтобы включить архивацию как для сеансов обмена мгновенными сообщениями, так и для конференций, выберите пункт **Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**.</span><span class="sxs-lookup"><span data-stu-id="22a17-122">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="22a17-123">Чтобы отключить архивацию для политики, щелкните **Отключить архивацию**.</span><span class="sxs-lookup"><span data-stu-id="22a17-123">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="22a17-124">Также в разделе **Новый параметр архивирования** выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="22a17-124">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="22a17-125">Чтобы заблокировать действия, когда архивирование невозможно, установите флажок **Block instant messaging (IM) or web conferencing sessions if archiving fails** (Блокировать сеансы обмена мгновенными сообщениями или веб-конференций, если не удается выполнить архивирование).</span><span class="sxs-lookup"><span data-stu-id="22a17-125">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="22a17-126">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="22a17-126">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="22a17-127">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="22a17-127">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="22a17-128">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="22a17-128">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="22a17-129">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="22a17-129">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="22a17-130">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="22a17-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

