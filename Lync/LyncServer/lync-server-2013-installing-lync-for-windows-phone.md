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
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="bf6f0-102">Установка Lync для Windows Phone в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf6f0-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf6f0-103">_**Тема последнего изменения:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="bf6f0-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="bf6f0-104">Lync 2013 для Windows Phone — это приложение, которое можно установить для пользователей и доступно в Windows Phone Marketplace.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="bf6f0-105">Установка Lync для Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="bf6f0-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="bf6f0-106">Вы можете подать пользователям возможность установить Lync 2013 для Windows Phone на своих устройствах, направив их на Windows Phone Marketplace по адресу <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="bf6f0-107">Если для публикации веб-служб Exchange используется запись DNS SRV</span><span class="sxs-lookup"><span data-stu-id="bf6f0-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="bf6f0-108">Для включения интеграции с Exchange для клиентов Lync некоторые организации публикуют URL-адрес служб Exchange, используя запись DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="bf6f0-109">В документе "Основные сведения и устранение неполадок при интеграции Exchange" в центре загрузки Microsoft [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)описаны сценарии, в которых это может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="bf6f0-110">Однако интеграция с Exchange для пользователей Windows Phone не будет работать в этом сценарии, так как платформа Windows Phone не поддерживает поиск SRV.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="bf6f0-111">Вам потребуется указать, что пользователи Windows Phone будут указывать URL веб-службы Exchange вместо того, чтобы разрешить телефону автоматически определять сервер.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="bf6f0-112">Попросите пользователей настроить параметры Lync на телефоне с Windows, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="bf6f0-113">На устройстве с Windows Phone в параметрах Lync щелкните экран **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="bf6f0-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="bf6f0-114">Переместить **сервер автоматически** **.**</span><span class="sxs-lookup"><span data-stu-id="bf6f0-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="bf6f0-115">Коснитесь пустого поля и введите полное доменное имя (FQDN) для веб-служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf6f0-116">Вы можете указать либо полное доменное имя (FQDN), либо полный URL-адрес сервера.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="bf6f0-117">При указании полного доменного имени протокол (https://) и путь к веб-службам Exchange (/ЕВС/ексчанже.асмкс) добавляются автоматически.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="bf6f0-118">Если путь к веб-службам Exchange отличается, вы можете указать полный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="bf6f0-119">Закройте экран.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="bf6f0-120">Проверка установки клиента для мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="bf6f0-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="bf6f0-121">После того как вы настроили клиент и войдете в свою учетную запись, выполните следующие проверки, чтобы убедиться, что установка Lync 2013 работает правильно на вашем мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="bf6f0-122">**Поиск контакта в корпоративном каталоге**</span><span class="sxs-lookup"><span data-stu-id="bf6f0-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="bf6f0-123">В списке контактов нажмите кнопку **Поиск** в нижней части экрана.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="bf6f0-124">Выполните поиск контакта, который существует только в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="bf6f0-125">Убедитесь, что имя контакта отображается в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="bf6f0-126">**Проверка функций обмена мгновенными сообщениями и сведений о присутствии**</span><span class="sxs-lookup"><span data-stu-id="bf6f0-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="bf6f0-127">В списке контактов выберите контакт.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="bf6f0-128">На карточке контакта коснитесь значка **мгновенное сообщение** .</span><span class="sxs-lookup"><span data-stu-id="bf6f0-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="bf6f0-129">Убедитесь, что окно программы обмена мгновенными сообщениями открывается и вы можете ввести и отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="bf6f0-130">**Проверка конференц-связи с телефонным подключением**</span><span class="sxs-lookup"><span data-stu-id="bf6f0-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="bf6f0-131">В Outlook Запланируйте собрание Lync.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="bf6f0-132">На мобильном устройстве откройте приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="bf6f0-133">Щелкните ссылку в собрании, чтобы присоединиться к нему.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="bf6f0-134">Ответьте на звонок службы конференций и убедитесь, что вы можете прослушивать звук.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="bf6f0-135">**Проверка push-уведомлений**</span><span class="sxs-lookup"><span data-stu-id="bf6f0-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="bf6f0-136">На мобильном устройстве пользователя A Войдите в Lync с помощью учетной записи пользователя A.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="bf6f0-137">Откройте другое приложение на мобильном устройстве.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="bf6f0-138">На другом клиенте Войдите в Lync с учетной записью пользователя B.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="bf6f0-139">Отправьте мгновенное сообщение от пользователя Б пользователю А.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="bf6f0-140">Убедитесь, что уведомление о мгновенном сообщении отображается на мобильном устройстве пользователя А.</span><span class="sxs-lookup"><span data-stu-id="bf6f0-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

