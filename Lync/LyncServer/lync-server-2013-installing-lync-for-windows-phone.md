---
title: 'Lync Server 2013: Установка Lync для Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 349a4b2609f3b810d0aa64c9e71786f309f21918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="d5615-102">Установка Lync для Windows Phone в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5615-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5615-103">_**Последнее изменение темы:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="d5615-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="d5615-104">Lync 2013 для Windows Phone — это приложение, устанавливаемое пользователем и доступное в Windows Phone Marketplace.</span><span class="sxs-lookup"><span data-stu-id="d5615-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="d5615-105">Установка Lync для Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="d5615-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="d5615-106">Вы можете поручить пользователям устанавливать Lync 2013 для Windows Phone на своих устройствах, направляя их на Windows Phone Marketplace по адресу <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span><span class="sxs-lookup"><span data-stu-id="d5615-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="d5615-107">Если вы используете запись DNS SRV для публикации веб-служб Exchange</span><span class="sxs-lookup"><span data-stu-id="d5615-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="d5615-108">Чтобы включить интеграцию с Exchange для клиентов Lync, некоторые организации публикуют URL-адрес веб-служб Exchange, используя запись DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="d5615-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="d5615-109">В документе "Основные сведения и устранение неполадок интеграции с Exchange", доступные в центре [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)загрузки Майкрософт по адресу, описываются сценарии, в которых это может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="d5615-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="d5615-110">Однако интеграция с Exchange для пользователей Windows Phone не будет работать в этом сценарии, так как платформа Windows Phone не поддерживает поиск SRV.</span><span class="sxs-lookup"><span data-stu-id="d5615-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="d5615-111">Пользователям Windows Phone необходимо указать URL-адрес веб-служб Exchange, а не разрешить телефону автоматически обнаруживать сервер.</span><span class="sxs-lookup"><span data-stu-id="d5615-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="d5615-112">Попросите пользователей настроить параметры Lync для своих телефонов с Windows, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d5615-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="d5615-113">В Windows Phone в разделе Параметры Lync выберите экран **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="d5615-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="d5615-114">Перемещение **сервера автоматического обнаружения** в **состояние "Выкл**.".</span><span class="sxs-lookup"><span data-stu-id="d5615-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="d5615-115">Коснитесь пустого поля и введите полное доменное имя (FQDN) или URL-адрес для веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5615-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5615-116">Можно указать полное доменное имя (FQDN) или полный URL-адрес сервера веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5615-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="d5615-117">Если указать полное доменное имя, протокол (https://) и путь веб-служб Exchange (/ЕВС/ексчанже.асмкс) будут добавляться автоматически.</span><span class="sxs-lookup"><span data-stu-id="d5615-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="d5615-118">Если путь к веб-службам Exchange отличается, можно указать полный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d5615-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="d5615-119">Закройте экран.</span><span class="sxs-lookup"><span data-stu-id="d5615-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="d5615-120">Проверка установки мобильного клиента</span><span class="sxs-lookup"><span data-stu-id="d5615-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="d5615-121">После настройки клиента и успешного входа выполните следующие тесты, чтобы убедиться, что установка Lync 2013 работает правильно на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="d5615-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="d5615-122">**Поиск контакта в корпоративном каталоге**</span><span class="sxs-lookup"><span data-stu-id="d5615-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="d5615-123">В списке Контакты нажмите кнопку **Поиск** в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d5615-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="d5615-124">Поиск контакта, который существует только в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="d5615-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="d5615-125">Убедитесь, что имя контакта отображается в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="d5615-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="d5615-126">**Тестирование обмена мгновенными сообщениями и сведений о присутствии**</span><span class="sxs-lookup"><span data-stu-id="d5615-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="d5615-127">В списке контактов выберите контакт.</span><span class="sxs-lookup"><span data-stu-id="d5615-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="d5615-128">В карточке контакта нажмите значок **обмена мгновенными сообщениями** .</span><span class="sxs-lookup"><span data-stu-id="d5615-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="d5615-129">Убедитесь, что отображается окно обмен мгновенными сообщениями и вы можете ввести и отправить мгновенное сообщение.</span><span class="sxs-lookup"><span data-stu-id="d5615-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="d5615-130">**Проверка конференц-связи с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="d5615-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="d5615-131">В Outlook Запланируйте собрание Lync.</span><span class="sxs-lookup"><span data-stu-id="d5615-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="d5615-132">На мобильном устройстве откройте приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="d5615-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="d5615-133">Щелкните ссылку в собрании, чтобы присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="d5615-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="d5615-134">Ответьте на звонок от службы конференций и убедитесь, что вы подключены к звуку собрания.</span><span class="sxs-lookup"><span data-stu-id="d5615-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="d5615-135">**Тестовые push-уведомления**</span><span class="sxs-lookup"><span data-stu-id="d5615-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="d5615-136">На мобильном устройстве пользователя а Войдите в Lync с учетной записью пользователя а.</span><span class="sxs-lookup"><span data-stu-id="d5615-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="d5615-137">Откройте другое приложение на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="d5615-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="d5615-138">На другом клиенте Войдите в Lync с учетной записью пользователя б.</span><span class="sxs-lookup"><span data-stu-id="d5615-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="d5615-139">Отправка мгновенного сообщения от пользователя б пользователю а.</span><span class="sxs-lookup"><span data-stu-id="d5615-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="d5615-140">Убедитесь, что уведомление о мгновенных сообщениях отображается на мобильном устройстве пользователя а.</span><span class="sxs-lookup"><span data-stu-id="d5615-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

