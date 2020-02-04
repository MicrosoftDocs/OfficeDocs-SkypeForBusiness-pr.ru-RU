---
title: 'Lync Server 2013: изменить или настроить простые URL-адреса'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="1c714-102">Изменить или настроить простые URL-адреса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c714-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c714-103">_**Тема последнего изменения:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="1c714-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="1c714-104">Для этой процедуры не требуется членство в группе локального администратора или привилегированного домена.</span><span class="sxs-lookup"><span data-stu-id="1c714-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="1c714-105">Войдите в систему как обычный пользователь.</span><span class="sxs-lookup"><span data-stu-id="1c714-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="1c714-106">Lync Server 2013 использует простые URL-адреса для прямого внутренних и внешних звонков к службам на сервере переднего плана или в директории, если она была развернута.</span><span class="sxs-lookup"><span data-stu-id="1c714-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="1c714-107">Дополнительные сведения об простых URL-адресах можно найти [в разделе Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="1c714-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="1c714-108">Вы можете выбрать формат для простых URL-адресов из нескольких вариантов.</span><span class="sxs-lookup"><span data-stu-id="1c714-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="1c714-109">Подробнее об этих параметрах можно узнать [в разделе Требования к DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="1c714-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="1c714-110">По умолчанию простые URL-адреса будут настраиваться в форме (например, простой URL-адрес для подключения): https://dialin.\<SIP domain\></span><span class="sxs-lookup"><span data-stu-id="1c714-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="1c714-111">Настройка простых URL-адресов</span><span class="sxs-lookup"><span data-stu-id="1c714-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="1c714-112">В построителе топологии щелкните правой кнопкой мыши узел **Lync Server** и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c714-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1c714-113">В области **простых URL-адресов** выберите для изменения свойство **URL-адреса телефонного доступа:** (Dial-in) или свойство **URL-адреса собраний:** (Meet). Затем нажмите команду **Изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="1c714-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="1c714-114">Установите для URL-адреса нужное значение и нажмите кнопку **ОК**, чтобы сохранить измененный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1c714-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="1c714-115">Приведенный здесь пример изменил URL-адрес для https://pool01.contoso.net/dialinподключения.</span><span class="sxs-lookup"><span data-stu-id="1c714-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="1c714-116">При необходимости тем же способом измените URL-адрес Meet.</span><span class="sxs-lookup"><span data-stu-id="1c714-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="1c714-117">Определение дополнительного URL-адреса Admin</span><span class="sxs-lookup"><span data-stu-id="1c714-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="1c714-118">В построителе топологии щелкните правой кнопкой мыши узел **Lync Server** и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c714-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="1c714-119">В диалоговом окне **URL-адрес администрирования** введите простой URL-адрес, который вы хотите использовать для административного доступа к панели управления Lync Server 2013, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1c714-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1c714-120">В качестве URL-адреса администрирования рекомендуется использовать максимально простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="1c714-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="1c714-121">Это самый простой вариант <STRONG> https://admin.</STRONG> &lt;Domain&gt;(домен).</span><span class="sxs-lookup"><span data-stu-id="1c714-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1c714-122">В случае изменения простого URL-адреса после исходного развертывания необходимо помнить, что такие изменения влияют на записи службы доменных имен (DNS) и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="1c714-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="1c714-123">Если это изменение повлияет на базу простого URL-адреса, необходимо также изменить записи DNS и сертификаты.</span><span class="sxs-lookup"><span data-stu-id="1c714-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="1c714-124">Например, https://lync.contoso.com/Meet чтобы https://meet.contoso.com изменить базовый URL-адрес с Lync.contoso.com на Meet.contoso.com, измените его, чтобы он ссылался на Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1c714-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="1c714-125">Если вы изменили простой URL- https://lync.contoso.com/Meet адрес https://lync.contoso.com/Meetingsс "на", то основной URL-адрес Lync.contoso.com остается таким же, поэтому изменения DNS или сертификата не требуются.</span><span class="sxs-lookup"><span data-stu-id="1c714-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="1c714-126">Однако при каждом изменении простого URL-адреса необходимо выполнить командлет <STRONG>Enable-кскомпутер</STRONG> на каждом из каталогов и на сервере переднего плана для регистрации изменения.</span><span class="sxs-lookup"><span data-stu-id="1c714-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c714-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1c714-127">See Also</span></span>


[<span data-ttu-id="1c714-128">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c714-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

