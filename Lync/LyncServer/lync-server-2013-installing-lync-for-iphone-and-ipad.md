---
title: 'Lync Server 2013: Установка Lync для iPhone и iPad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0383fd4aa389912a9942d7cafd7ac22fdc4f477
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a><span data-ttu-id="baed1-102">Установка Lync для iPhone и iPad в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baed1-102">Installing Lync for iPhone and iPad in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baed1-103">_**Тема последнего изменения:** 2014-03-10_</span><span class="sxs-lookup"><span data-stu-id="baed1-103">_**Topic Last Modified:** 2014-03-10_</span></span>

<span data-ttu-id="baed1-104">Lync 2013 для iPhone и Lync 2013 для iPad — это приложения, устанавливаемые пользователем, которые доступны в магазине Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="baed1-104">Lync 2013 for iPhone and Lync 2013 for iPad are user-installable applications that are available in the Apple App Store.</span></span>

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a><span data-ttu-id="baed1-105">Установка Lync для iPhone и Lync для iPad</span><span class="sxs-lookup"><span data-stu-id="baed1-105">Installing Lync for iPhone and Lync for iPad</span></span>

<span data-ttu-id="baed1-106">Вы можете подать пользователям возможность установить Lync 2013 для iPhone и Lync 2013 для iPad, перенаправив их на свои устройства из магазина приложений.</span><span class="sxs-lookup"><span data-stu-id="baed1-106">You can instruct your users to install Lync 2013 for iPhone and Lync 2013 for iPad by directing them to the App Store from their devices.</span></span> <span data-ttu-id="baed1-107">Магазин приложений для каждого устройства также доступен в сети.</span><span class="sxs-lookup"><span data-stu-id="baed1-107">The App Store for each device is also available online.</span></span>

  - <span data-ttu-id="baed1-108">Lync для iPhone доступен в магазине App Store \< <span></span>TTP://www.Apple.com/iPhone/from-the-App-Store/></span><span class="sxs-lookup"><span data-stu-id="baed1-108">Lync for iPhone is available in the App Store at \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/></span></span>

  - <span data-ttu-id="baed1-109">Lync для iPad доступен в магазине приложений на \< нт<span></span>TP://www.Apple.com/iPad/from-the-App-Store/></span><span class="sxs-lookup"><span data-stu-id="baed1-109">Lync for iPad is available in the App Store at \< ht<span></span>tp://www.apple.com/ipad/from-the-app-store/></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="baed1-110">Пользователи iPhone, которые не установили приложение Lync 2013 и которые пытаются присоединиться к собранию Lync из приглашения на собрание, будут перенаправляться на страницу средства запуска присоединения.</span><span class="sxs-lookup"><span data-stu-id="baed1-110">iPhone users who have not installed the Lync 2013 app and who try to join a Lync meeting from a meeting invitation will be redirected to a Join Launcher page.</span></span> <span data-ttu-id="baed1-111">На этой странице содержится ссылка для установки приложения Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="baed1-111">This page contains a link for installing the Lync 2013 app.</span></span> <span data-ttu-id="baed1-112">Однако вместо того чтобы перенаправлять пользователя в App Store, эта ссылка открывает пустую страницу браузера Safari.</span><span class="sxs-lookup"><span data-stu-id="baed1-112">However, instead of directing the user to the App Store, this link opens a blank Safari browser page.</span></span> <span data-ttu-id="baed1-113">Для решения этой проблемы пользователь может выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="baed1-113">The user can do one of two things to work around this issue:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="baed1-114">Нажмите кнопку " <STRONG>домой</STRONG> ", чтобы отправить страницу Safari на задний план, а затем откройте браузер Safari.</span><span class="sxs-lookup"><span data-stu-id="baed1-114">Use the <STRONG>Home</STRONG> button to send the Safari page to the background, and then reopen Safari.</span></span> <span data-ttu-id="baed1-115">Когда появится уведомление "открыть эту страницу в App Store", нажмите кнопку <STRONG>Открыть</STRONG> , чтобы перейти в приложение Lync 2013 download в магазине App Store.</span><span class="sxs-lookup"><span data-stu-id="baed1-115">When the notification “Open this page in App Store” appears, tap <STRONG>Open</STRONG> to be directed to Lync 2013 download in the App Store.</span></span></P>
> <LI>
> <P><span data-ttu-id="baed1-116">Вручную Откройте App Store, выполните поиск по запросу "Lync 2013" и скачайте приложение.</span><span class="sxs-lookup"><span data-stu-id="baed1-116">Manually open the App Store, search for "Lync 2013," and download the app.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="baed1-117">Проверка установки клиента для мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="baed1-117">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="baed1-118">После того как вы настроили клиент и Войди в систему, выполните следующие проверки, чтобы убедиться, что установка Lync правильно работает на вашем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="baed1-118">After you configure the client and sign in successfully, use the following tests to verify that your Lync installation is working correctly on your mobile device.</span></span>

<span data-ttu-id="baed1-119">**Поиск контакта в корпоративном каталоге**</span><span class="sxs-lookup"><span data-stu-id="baed1-119">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="baed1-120">В списке контактов коснитесь внутри строки поиска в верхней части экрана и начните ввод имени контакта, присутствующего в глобальном списке адресов (GAL).</span><span class="sxs-lookup"><span data-stu-id="baed1-120">In the Contacts list, tap inside the search bar at the top, and begin typing the name of a contact that exists only in the global address list (GAL).</span></span>

2.  <span data-ttu-id="baed1-121">Убедитесь, что имя контакта отображается в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="baed1-121">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="baed1-122">**Проверка функций обмена мгновенными сообщениями и сведений о присутствии**</span><span class="sxs-lookup"><span data-stu-id="baed1-122">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="baed1-123">В списке контактов выберите контакт.</span><span class="sxs-lookup"><span data-stu-id="baed1-123">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="baed1-124">На карточке контакта коснитесь значка **мгновенное сообщение** .</span><span class="sxs-lookup"><span data-stu-id="baed1-124">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="baed1-125">Убедитесь, что окно программы обмена мгновенными сообщениями открывается и вы можете ввести и отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="baed1-125">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="baed1-126">**Проверка конференц-связи с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="baed1-126">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="baed1-127">В Outlook Запланируйте собрание Lync.</span><span class="sxs-lookup"><span data-stu-id="baed1-127">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="baed1-128">На мобильном устройстве откройте приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="baed1-128">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="baed1-129">Щелкните ссылку в собрании, чтобы присоединиться к нему.</span><span class="sxs-lookup"><span data-stu-id="baed1-129">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="baed1-130">Ответьте на звонок от службы конференц-связи и убедитесь, что вы подключены к звуковому каналу собрания.</span><span class="sxs-lookup"><span data-stu-id="baed1-130">Answer the call from the conference service and verify that you are connected to the meeting audio.</span></span>

<span data-ttu-id="baed1-131">**Проверка push-уведомлений**</span><span class="sxs-lookup"><span data-stu-id="baed1-131">**Test push notifications**</span></span>

1.  <span data-ttu-id="baed1-132">На мобильном устройстве пользователя A Войдите в Lync с помощью учетной записи пользователя A.</span><span class="sxs-lookup"><span data-stu-id="baed1-132">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="baed1-133">Откройте другое приложение на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="baed1-133">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="baed1-134">На другом клиенте Войдите в Lync с учетной записью пользователя B.</span><span class="sxs-lookup"><span data-stu-id="baed1-134">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="baed1-135">Отправьте мгновенное сообщение от пользователя Б пользователю А.</span><span class="sxs-lookup"><span data-stu-id="baed1-135">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="baed1-136">Убедитесь, что уведомление о мгновенном сообщении отображается на мобильном устройстве пользователя А.</span><span class="sxs-lookup"><span data-stu-id="baed1-136">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

