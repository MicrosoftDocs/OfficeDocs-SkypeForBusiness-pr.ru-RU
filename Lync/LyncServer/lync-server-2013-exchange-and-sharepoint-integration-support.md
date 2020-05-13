---
title: 'Lync Server 2013: поддержка интеграции Exchange и SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 262e31ac6049920ca4e327f50dccaae18d69a2f5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="ad1f7-102">Поддержка интеграции Exchange и SharePoint в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad1f7-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad1f7-103">_**Последнее изменение темы:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="ad1f7-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="ad1f7-104">Lync Server 2013 и Lync 2013 могут безопасно и эффективно взаимодействовать с другими приложениями и серверными продуктами, в том числе Office 2013, Exchange Server 2013, Exchange Server 2016 и SharePoint, если вы интегрируете эти продукты.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="ad1f7-105">Интеграция Lync Server 2013 и Office предоставляет пользователям доступ в контексте обмена мгновенными сообщениями, расширенных возможностей присутствия, телефонии и конференц-связи в Lync.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="ad1f7-106">Пользователи Office могут получать доступ к функциям Lync из клиента Outlook 2013 для обмена сообщениями и совместной работы, а также из других программ Office или из страницы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="ad1f7-107">Пользователи также могут просматривать записи бесед Lync в папке "Журнал бесед Outlook".</span><span class="sxs-lookup"><span data-stu-id="ad1f7-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="ad1f7-108">При интеграции с Exchange 2013, Exchange 2016 или Exchange Online Lync Server 2013 также поддерживает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="ad1f7-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="ad1f7-109">Единое хранилище контактов, которое позволяет пользователям хранить все контактные данные в Exchange или Exchange Online, чтобы информация была доступна глобально для Lync 2013, Exchange, Outlook и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="ad1f7-110">Журнал бесед и история веб-конференций, которые хранятся в папках пользователей Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="ad1f7-111">Архивированный контент из Lync, например, Обмен мгновенными сообщениями и контент собрания, можно хранить в хранилище Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad1f7-112">Lync Server 2013 поддерживает интеграцию с предыдущими версиями Microsoft Exchange Server и SharePoint Server, но не все функции поддерживаются в этих предыдущих версиях, таких как интеграция хранилища архивации с Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="ad1f7-113">Если вы переносите пользователей в Exchange 2013 или Exchange 2016, вы можете использовать как хранилище Exchange, так и хранилище Lync Server на промежуточной основе.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="ad1f7-114">Постоянное использование хранилища Exchange и сервера Lync Server не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="ad1f7-115">Для интеграции Lync Server 2013 с Exchange Server и SharePoint Server требуется межсерверная проверка подлинности между серверами, работающими под управлением Lync Server 2013, Exchange Server и SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="ad1f7-116">Lync Server 2013 поддерживает протокол OAuth (открытая авторизация) для проверки подлинности и авторизации "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="ad1f7-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ad1f7-117">Для межсерверной проверки подлинности между двумя локальными серверами Майкрософт нет необходимости использовать сторонний сервер маркеров.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="ad1f7-118">Lync Server 2013, Exchange Server и SharePoint Server имеют встроенный сервер маркеров, который можно использовать в целях проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="ad1f7-119">Например, Lync Server 2013 может выдать и подписать маркер безопасности самостоятельно и использовать этот маркер при взаимодействии с Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="ad1f7-120">В этом случае не нужно использовать сторонний сервер маркеров.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="ad1f7-121">Lync Server 2013 поддерживает два сценария межсерверной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="ad1f7-122">К ним относятся Настройка межсерверной проверки подлинности между следующими серверами:</span><span class="sxs-lookup"><span data-stu-id="ad1f7-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="ad1f7-123">Локальная установка Lync Server 2013 и локальная установка Exchange Server 2013, Exchange Server 2016 и/или SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="ad1f7-124">Сочетание компонентов Office (например, между Microsoft Exchange 365 и Microsoft Lync Server 365 или между Microsoft Lync Server 365 и Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="ad1f7-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad1f7-125">Проверка подлинности между серверами между локальным сервером и компонентом Microsoft 365 или Office 365 не поддерживается в этом выпуске Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-125">Server-to-server authentication between an on-premises server and a Microsoft 365 or Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="ad1f7-126">Помимо прочего, это означает, что невозможно настроить межсерверную проверку подлинности между локальной установкой Lync Server 2013 и Microsoft Exchange 365.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="ad1f7-127">Дополнительные сведения о проверке подлинности между серверами можно найти в статье [Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ad1f7-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
