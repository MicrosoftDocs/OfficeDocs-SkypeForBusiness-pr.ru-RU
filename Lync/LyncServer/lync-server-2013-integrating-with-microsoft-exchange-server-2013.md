---
title: 'Lync Server 2013: интеграция с Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489c5023ab995700762fa5e19ba361df1b49a6b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="3b60e-102">Интеграция Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b60e-103">_**Последнее изменение темы:** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="3b60e-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="3b60e-104">Exchange и Lync Server имеют длительную историю интеграции и совместимости.</span><span class="sxs-lookup"><span data-stu-id="3b60e-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="3b60e-105">Эта интеграция наиболее заметна в соответствующем клиентском приложении.</span><span class="sxs-lookup"><span data-stu-id="3b60e-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="3b60e-106">Например, сведения о присутствии Lync можно указать в Microsoft Outlook; Аналогично, Lync может использовать календарь Outlook для автоматического обновления сведений о присутствии.</span><span class="sxs-lookup"><span data-stu-id="3b60e-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="3b60e-107">(Например, Lync может изменить свое состояние на "занято" в любое время, когда в календаре отображается запланированное собрание.) Несмотря на то, что для работы с Lync Server (или наоборот) не требуется запускать Exchange, существует небольшое мнение о том, что использование двух продуктов совместно епитомизес очень важное значение термина "более эффективная совместная работа".</span><span class="sxs-lookup"><span data-stu-id="3b60e-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="3b60e-108">Это особенно относится к выпуску Microsoft Lync Server 2013 и Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3b60e-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="3b60e-109">Помимо функций, таких как единая система обмена сообщениями и обмен мгновенными сообщениями и сведениями о присутствии, которые находятся в Microsoft Exchange Server 2010 и Microsoft Lync Server 2010, выпуски серверных продуктов с 2013 для имеют ряд новых возможностей.</span><span class="sxs-lookup"><span data-stu-id="3b60e-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="3b60e-110">Эти возможности включают в себя следующие моменты:</span><span class="sxs-lookup"><span data-stu-id="3b60e-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="3b60e-111">**Интеграция архивации Lync**.</span><span class="sxs-lookup"><span data-stu-id="3b60e-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="3b60e-112">В Lync Server 2013 администраторы по-прежнему имеют возможность сохранять записи о мгновенных сообщениях и веб-конференциях в SQL Server (аналогично тому, как эти записи были архивированы в Lync Server 2010).</span><span class="sxs-lookup"><span data-stu-id="3b60e-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="3b60e-113">Кроме того, администраторы могут использовать записи архивов в Exchange 2013, сохраняя эти записи в почтовых ящиках отдельных пользователей точно так же, как и для обмена сообщениями в архиве Exchange.</span><span class="sxs-lookup"><span data-stu-id="3b60e-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="3b60e-114">Это означает, что вы можете использовать один репозиторий для всех электронных коммуникаций (от Exchange и Lync Server), что значительно упрощает поиск и извлечение таких архивных данных, которые должны возникать.</span><span class="sxs-lookup"><span data-stu-id="3b60e-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="3b60e-115">**Единое хранилище контактов**.</span><span class="sxs-lookup"><span data-stu-id="3b60e-115">**Unified Contact Store**.</span></span> <span data-ttu-id="3b60e-116">В Lync Server 2010 пользователям приходится поддерживать отдельные списки контактов в Outlook и Lync; на самом деле, чтобы обеспечить наличие одних и тех же контактов в обоих продуктах, для которых необходимо поддерживать повторяющиеся списки контактов, один для Outlook и один для Lync.</span><span class="sxs-lookup"><span data-stu-id="3b60e-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="3b60e-117">Однако при использовании Lync Server 2013 контакты пользователей могут храниться в Exchange 2013 и в едином хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3b60e-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="3b60e-118">Использование одного хранилища контактов позволяет пользователям хранить только один набор контактов с тем же набором контактов, который доступен в Lync 2013, Outlook 2013 и Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="3b60e-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="3b60e-119">**Планирование собраний Lync из OWA**.</span><span class="sxs-lookup"><span data-stu-id="3b60e-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="3b60e-120">С помощью Lync Server 2013 и интеграции с Exchange 2013 пользователи могут планировать собрания Lync из Outlook Web Access 2013.</span><span class="sxs-lookup"><span data-stu-id="3b60e-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="3b60e-121">**Фотографии с высоким разрешением**.</span><span class="sxs-lookup"><span data-stu-id="3b60e-121">**High resolution photos**.</span></span> <span data-ttu-id="3b60e-122">Lync 2010 может отображать только небольшие фотографии контактов. Это вызвано тем, что эти фотографии хранились в Active Directory, а Active Directory накладывает ограничение размера 48 на 48 пикселя для сохраненных фотографий.</span><span class="sxs-lookup"><span data-stu-id="3b60e-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="3b60e-123">Тем не менее, в Lync Server 2013 фотографии могут храниться в Microsoft Exchange. Это позволяет использовать фотографии высокого разрешения в размере 648 x 648 пикселей.</span><span class="sxs-lookup"><span data-stu-id="3b60e-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="3b60e-124">Как можно было ожидать, Lync 2013 был обновлен, чтобы иметь возможность отображать фотографии с высоким разрешением.</span><span class="sxs-lookup"><span data-stu-id="3b60e-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="3b60e-125">Помните, что для этих новых функций требуется использование Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3b60e-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="3b60e-126">Кроме того, пользователи, которые пожелают использовать все преимущества этих новых возможностей, должны иметь учетные записи на Lync Server 2013 и Exchange 2013, а также должны использовать последние версии клиентского программного обеспечения (например, Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="3b60e-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="3b60e-127">Например, единое хранилище контактов недоступно для пользователей, размещенных в Lync Server 2010; Аналогично, фотографии с высоким разрешением не могут отображаться в Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="3b60e-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="3b60e-128">В этой документации представлены сведения о интеграции Lync Server 2013 и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="3b60e-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="3b60e-129">включает пошаговые инструкции по включению новых функций, таких как интеграция архивации и единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="3b60e-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="3b60e-130">В этой документации не рассматриваются первоначальная установка и настройка этих двух продуктов.</span><span class="sxs-lookup"><span data-stu-id="3b60e-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="3b60e-131">Дополнительные сведения о развертывании Lync Server 2013 см. в статье Lync Server 2013 [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)Tech Center по адресу.</span><span class="sxs-lookup"><span data-stu-id="3b60e-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="3b60e-132">Для получения дополнительных сведений о развертывании Exchange 2013 посетите центр технической поддержки [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)Exchange 2013 по адресу.</span><span class="sxs-lookup"><span data-stu-id="3b60e-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b60e-133">Содержание</span><span class="sxs-lookup"><span data-stu-id="3b60e-133">In This Section</span></span>

[<span data-ttu-id="3b60e-134">Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="3b60e-135">Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="3b60e-136">Настройка Microsoft Lync Server 2013 для использования архивации Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="3b60e-137">Настройка Microsoft SharePoint Server 2013 для поиска архивных данных Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="3b60e-138">Настройка Microsoft Lync Server 2013 для использования единого хранилища контактов</span><span class="sxs-lookup"><span data-stu-id="3b60e-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="3b60e-139">Настройка использования фотографий высокого разрешения в Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="3b60e-140">Настройка единой системы обмена сообщениями Microsoft Exchange Server 2013 для голосовой почты Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="3b60e-141">Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="3b60e-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

