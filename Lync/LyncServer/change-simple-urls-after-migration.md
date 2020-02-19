---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e96c6a1d33c9c50208c7cdea628b2c4464a7b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="11bb3-102">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="11bb3-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11bb3-103">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="11bb3-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="11bb3-104">Lync Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="11bb3-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="11bb3-p101">URL-адрес **собраний** (meet) используется в качестве основного URL-адреса для всех конференций на сайте или в организации. Простой URL-адрес собраний делает ссылки на присоединение к собраниям более понятными и удобными для обмена и распространения.</span><span class="sxs-lookup"><span data-stu-id="11bb3-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="11bb3-p102">URL-адрес **телефонного подключения** (dialin) обеспечивает доступ к веб-странице "Параметры конференц-связи с телефонным подключением". Простой URL-адрес телефонного подключения включается во все приглашения на собрания. Таким образом пользователи, которые хотят подключиться к собранию с помощью телефона, могут найти в нем необходимый номер телефона и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="11bb3-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="11bb3-109">**Администратор** обеспечивает быстрый доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="11bb3-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="11bb3-110">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="11bb3-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="11bb3-111">После перехода на Lync Server 2013 необходимо знать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="11bb3-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="11bb3-112">Если устаревший директор Lync Server 2010 остается в использовании в топологии, изменять простые URL-адреса не требуется.</span><span class="sxs-lookup"><span data-stu-id="11bb3-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="11bb3-113">Если после миграции служба каталогов Lync Server 2010 была удалена из топологии, DNS-записи простых URL-адресов должны быть обновлены, чтобы указать один из пулов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="11bb3-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="11bb3-114">Однако при любом изменении простого URL-адреса вам необходимо выполнить командлет Enable-CsComputer на каждом Директоре и сервере переднего плана, чтобы зарегистрировать это изменение.</span><span class="sxs-lookup"><span data-stu-id="11bb3-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="11bb3-115">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="11bb3-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="11bb3-116">**Обновление простого URL-адреса собраний**</span><span class="sxs-lookup"><span data-stu-id="11bb3-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="11bb3-117">В построителе топологий щелкните правой кнопкой мыши верхний узел **Lync Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="11bb3-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="11bb3-118">В левой области выберите **простые URL** -адреса, а затем в разделе URL **-адреса собраний:** выберите URL-адрес соответствия, а затем щелкните **изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="11bb3-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="11bb3-119">Задайте для URL-адреса требуемое значение и нажмите кнопку **ОК**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="11bb3-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="11bb3-120">**Обновление простого URL-адреса администратора**</span><span class="sxs-lookup"><span data-stu-id="11bb3-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="11bb3-121">В построителе топологий щелкните правой кнопкой мыши верхний узел **Lync Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="11bb3-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="11bb3-122">Выберите **простые URL-адреса** в левой области, а затем в поле **URL-адрес административного доступа** введите простой URL-адрес, который требуется использовать для административного доступа к панели управления Lync Server 2013, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="11bb3-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="11bb3-123">Рекомендуется использовать самый простой URL-адрес для административного доступа.</span><span class="sxs-lookup"><span data-stu-id="11bb3-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="11bb3-124">Самый простой вариант — <STRONG> https://admin.</STRONG> &lt;Domain&gt;(домен).</span><span class="sxs-lookup"><span data-stu-id="11bb3-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11bb3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="11bb3-125">See Also</span></span>


[<span data-ttu-id="11bb3-126">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11bb3-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

