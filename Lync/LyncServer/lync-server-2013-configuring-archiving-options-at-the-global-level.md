---
title: 'Lync Server 2013: Настройка параметров архивации на глобальном уровне'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d2bcd5265d9e8af53cb2dab608bbe08f2902330
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="7a79a-102">Настройка параметров архивации на глобальном уровне в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a79a-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a79a-103">_**Последнее изменение темы:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="7a79a-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="7a79a-104">При добавлении архивации в топологию и публикации топологии в Lync Server создается Глобальная конфигурация для архивации.</span><span class="sxs-lookup"><span data-stu-id="7a79a-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="7a79a-105">По умолчанию в глобальной конфигурации архивация отключена.</span><span class="sxs-lookup"><span data-stu-id="7a79a-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="7a79a-106">Глобальная конфигурация задает параметры, включенные для всего развертывания, если не заданы параметры на уровне сайта или пула, которые переопределяют глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7a79a-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="7a79a-107">Сведения о том, как работает Настройка архивации, в том числе иерархия для конфигураций глобальных, сайтов и пулов, приведены в статье Планирование, документация по развертыванию и документация по работе [при архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) .</span><span class="sxs-lookup"><span data-stu-id="7a79a-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a79a-108">Перед включением архивации необходимо задать все требуемые параметры с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="7a79a-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="7a79a-109">Настройка параметров архивации на глобальном уровне</span><span class="sxs-lookup"><span data-stu-id="7a79a-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="7a79a-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7a79a-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7a79a-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a79a-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7a79a-112">Дополнительные сведения о различных методах, которые можно использовать для запуска панели управления Lync Server 2013, можно найти в статье [Open the Lync server 2013 Tools администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7a79a-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7a79a-113">В левой панели навигации щелкните **мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="7a79a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="7a79a-114">На странице **Конфигурация архивации** последовательно щелкните **Глобальная**, **Изменить** и **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="7a79a-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7a79a-115">На странице **Изменение параметров архивации — глобальный уровень** выберите в раскрывающемся списке **Параметр архивации** один из следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="7a79a-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="7a79a-116">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="7a79a-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="7a79a-117">**Архивировать сеансы обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="7a79a-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="7a79a-118">**Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="7a79a-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="7a79a-119">На странице **Изменение параметров архивации — глобальный уровень** выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="7a79a-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="7a79a-120">Чтобы заблокировать коммуникации, когда архивация недоступна, установите флажок **Блокировать мгновенные сообщения или сеансы веб-конференций при сбое архивации**.</span><span class="sxs-lookup"><span data-stu-id="7a79a-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="7a79a-121">Чтобы использовать Microsoft Exchange Server для хранения архивных данных, установите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="7a79a-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="7a79a-122">Чтобы включить удаление данных, установите флажок **Включить удаление архивных данных**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="7a79a-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="7a79a-123">Чтобы задать удаление после определенного числа дней, щелкните **Удалять экспортированные архивные данные и сохраненные архивные данные максимум в течение (дней)**, а затем задайте число дней.</span><span class="sxs-lookup"><span data-stu-id="7a79a-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="7a79a-124">Чтобы ограничить удаление только теми данными, которые были экспортированы, щелкните **Удалять только экспортированные архивные данные**.</span><span class="sxs-lookup"><span data-stu-id="7a79a-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="7a79a-125">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="7a79a-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

