---
title: 'Lync Server 2013: изменение или Настройка простых URL-адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e77d5ddf74d43cd277a701608e801a65262c929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="88091-102">Изменение или Настройка простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88091-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88091-103">_**Последнее изменение темы:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="88091-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="88091-p101">Для этой процедуры не требуется членство в локальной группе администраторов или группе привилегированного домена. Вы должны войти на компьютер в качестве обычного пользователя.</span><span class="sxs-lookup"><span data-stu-id="88091-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="88091-106">Lync Server 2013 использует простые URL-адреса для направления внутренних и внешних вызовов служб на сервере переднего плана или в директоре, если она была развернута.</span><span class="sxs-lookup"><span data-stu-id="88091-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="88091-107">Более подробную информацию об простых URL-адресах можно узнать [в статье Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="88091-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="88091-108">Можно выбрать формат для простых URL-адресов из нескольких вариантов.</span><span class="sxs-lookup"><span data-stu-id="88091-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="88091-109">Подробнее об этих параметрах можно узнать в статье [требования к DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="88091-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="88091-110">По умолчанию простые URL-адреса будут настроены в форме (например, простой URL-адрес для телефонного подключения) https://dialin.\<SIP : domain\></span><span class="sxs-lookup"><span data-stu-id="88091-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="88091-111">Настройка простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="88091-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="88091-112">В построителе топологий щелкните узел **Lync Server** правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="88091-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="88091-113">В области **простые URL-адреса** выберите **URL-адреса для доступа к телефонной линии:** (с телефонным подключением) или **URL-адреса собраний:** (соответствие), а затем щелкните **изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="88091-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="88091-114">Задайте для URL-адреса требуемое значение и нажмите кнопку **ОК**, чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="88091-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="88091-115">В приведенном здесь примере изменился URL-адрес для телефонного подключения на https://pool01.contoso.net/dialin.</span><span class="sxs-lookup"><span data-stu-id="88091-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="88091-116">При необходимости тем же способом измените URL-адрес Meet.</span><span class="sxs-lookup"><span data-stu-id="88091-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="88091-117">Определение дополнительного URL-адреса Admin</span><span class="sxs-lookup"><span data-stu-id="88091-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="88091-118">В построителе топологий щелкните узел **Lync Server** правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="88091-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="88091-119">В поле **URL-адрес административного доступа** введите простой URL-адрес, который требуется использовать для административного доступа к панели управления Lync Server 2013, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="88091-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="88091-120">Рекомендуется использовать самый простой URL-адрес для административного доступа.</span><span class="sxs-lookup"><span data-stu-id="88091-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="88091-121">Самый простой вариант — <STRONG> https://admin.</STRONG> &lt;Domain&gt;(домен).</span><span class="sxs-lookup"><span data-stu-id="88091-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="88091-122">Если простые URL-адреса меняются после развертывания, то необходимо подумать о том, какие изменения простых URL-адресов повлияют на записи DNS и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="88091-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="88091-123">Если изменение касается базового простого URL-адреса, то придется также изменить записи DNS и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="88091-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="88091-124">Например, изменение с https://lync.contoso.com/Meet для https://meet.contoso.com изменения базового URL-адреса с Lync.contoso.com на Meet.contoso.com, поэтому необходимо изменить записи DNS и сертификаты, чтобы они ссылались на Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="88091-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="88091-125">Если вы изменили простой URL- https://lync.contoso.com/Meet адрес https://lync.contoso.com/Meetingsс на, то базовый URL-адрес Lync.contoso.com остается прежним, поэтому не требуются изменения DNS или сертификата.</span><span class="sxs-lookup"><span data-stu-id="88091-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="88091-126">Однако при изменении простого URL-адреса необходимо выполнить командлет <STRONG>Enable-CsComputer</STRONG> на каждом директоре и сервере переднего плана, чтобы зарегистрировать изменение.</span><span class="sxs-lookup"><span data-stu-id="88091-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88091-127">См. также</span><span class="sxs-lookup"><span data-stu-id="88091-127">See Also</span></span>


[<span data-ttu-id="88091-128">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88091-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

