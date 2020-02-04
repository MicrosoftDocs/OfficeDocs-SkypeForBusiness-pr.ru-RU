---
title: 'Lync Server 2013: Установка системы управления комнатой на Lync Web портал'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcfc78429ef021afcb0ed286ad86a39e63bfbf62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="fe83f-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe83f-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe83f-103">_**Тема последнего изменения:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="fe83f-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="fe83f-104">Вы можете скачать веб-портал для Microsoft Lync Room System из центра загрузки Майкрософт по адресу [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span><span class="sxs-lookup"><span data-stu-id="fe83f-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="fe83f-105">Чтобы установить веб-портал для управления комнатой на Lync, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fe83f-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="fe83f-106">Настройте порт доверенного приложения, выполнив следующий командлет в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe83f-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="fe83f-107">Чтобы установить портал комнаты для собраний, скачайте **линкрумадминпортал. exe** и запустите его в качестве администратора.</span><span class="sxs-lookup"><span data-stu-id="fe83f-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="fe83f-108">Откройте файл Web.config в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="fe83f-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="fe83f-109">% Program Files\\% Microsoft Lync Server\\2013 веб\\-компоненты для\\собраний портал\\комнаты</span><span class="sxs-lookup"><span data-stu-id="fe83f-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="fe83f-110">В файле Web. config измените Порталусернаме на имя пользователя, созданное на этапе 2, в разделе "Настройка предварительных требований для портала администрирования системы комнат в Lync" (рекомендуемое имя на этапе — Лрсапп):</span><span class="sxs-lookup"><span data-stu-id="fe83f-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="fe83f-111">Поскольку портал администрирования ЛРС является надежным приложением, вам не нужно указывать пароль в конфигурации портала.</span><span class="sxs-lookup"><span data-stu-id="fe83f-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="fe83f-112">Если этот пользователь использует регистратор, отличный от локального, необходимо указать регистратор, добавив в файл Web.Config следующую строку:</span><span class="sxs-lookup"><span data-stu-id="fe83f-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="fe83f-113">Если используется порт, отличный от 5061, добавьте в файл Web.Config следующую строку: </span><span class="sxs-lookup"><span data-stu-id="fe83f-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="fe83f-114">Проверка установки системы управления комнатой Lync Web портал</span><span class="sxs-lookup"><span data-stu-id="fe83f-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="fe83f-115">Чтобы проверить, установлен ли веб-портал для управления комнатой на Lync, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fe83f-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="fe83f-116">Откройте следующий URL-адрес на сервере переднего плана:</span><span class="sxs-lookup"><span data-stu-id="fe83f-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="fe83f-117">https://\<Fe-Server\>/ЛРС</span><span class="sxs-lookup"><span data-stu-id="fe83f-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="fe83f-118">При этом не должно выводиться никаких сообщений об ошибках, как на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="fe83f-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="fe83f-119">![Экран входа в портал администрирования системы комнат Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Экран входа в портал администрирования системы комнат Lync")</span><span class="sxs-lookup"><span data-stu-id="fe83f-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="fe83f-120">Если никаких сообщений при этом не выводится, попробуйте перейти по следующему URL-адресу с любого другого компьютера в топологии:</span><span class="sxs-lookup"><span data-stu-id="fe83f-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="fe83f-121">https://\<Fe-Server\>/ЛРС</span><span class="sxs-lookup"><span data-stu-id="fe83f-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="fe83f-122">Для доступа к странице вам потребуется добавить записи DNS, как описано в разделе "необходимые записи DNS для автоматического входа в клиент" [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span><span class="sxs-lookup"><span data-stu-id="fe83f-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

