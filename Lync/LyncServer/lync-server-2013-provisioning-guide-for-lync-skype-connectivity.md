---
title: 'Lync Server 2013: руководство по подготовке взаимодействия Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f94da566e4322f9b8d1d039441c561f5ed60f6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="99122-102">Руководство по подготовке взаимодействия Lync-Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99122-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99122-103">_**Тема последнего изменения:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="99122-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="99122-p101">Lync Server 2013 поддерживает возможность подключения к Skype. Благодаря этому пользователи Lync 2013 могут добавлять контакты Skype, используя учетные записи Microsoft (MSA) пользователей Skype. Клиенты Skype также могут добавлять пользователей Lync в свои списки контактов. В соответствии с политиками, заданными на сервере Lync Server, пользователи Lync и Skype смогут обмениваться мгновенными сообщениями, просматривать сведения о присутствии друг друга, а также совершать голосовые звонки и видеозвонки. Интеграция Lync и Skype также реализована в системе Lync Online и может быть активирована для клиентов Lync Online в центре администрирования Lync на портале Office 365.</span><span class="sxs-lookup"><span data-stu-id="99122-p101">Lync Server 2013 supports connectivity with Skype. This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA). Skype clients can also add Lync users to their contact list. Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls. Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="99122-p102">Если сервер Lync Server уже настроен для взаимодействия с приложением Windows Messenger с использованием общедоступной службы обмена сообщениями (PIC), это означает, что интеграция Lync и Skype уже настроена в вашей среде, и вам достаточно будет переименовать существующую запись общедоступной службы обмена сообщениями Messenger в Skype. Подробные сведения см. в разделе, посвященном настройке параметров поставщика общедоступной службы обмена сообщениями Skype для Lync, далее в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="99122-p102">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype. For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99122-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="99122-112">In This Section</span></span>

  - [<span data-ttu-id="99122-113">Примечание о соединении Lync — Skype в Lync Server 2013 для пользователей Lync Online</span><span class="sxs-lookup"><span data-stu-id="99122-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="99122-114">Доступ к сайту предоставления общедоступной службы обмена мгновенными сообщениями из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99122-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="99122-115">Обеспечение взаимодействия Lync и Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99122-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="99122-116">Взаимодействие между конечными пользователями Lync и Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99122-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="99122-117">Часто задаваемые вопросы: подготовка сервера Lync Server 2013 для подключения Skype</span><span class="sxs-lookup"><span data-stu-id="99122-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

