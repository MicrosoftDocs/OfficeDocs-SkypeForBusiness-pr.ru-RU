---
title: 'Lync Server 2013: руководство по подготовке к подключению к Lync-Skype'
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
ms.openlocfilehash: 073d7c583c6d159e1b262421e441a56c9d081928
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513166"
---
# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="e696c-102">Руководство по подготовке к Lync-Skype подключениям в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e696c-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e696c-103">_**Последнее изменение темы:** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="e696c-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="e696c-104">Lync Server 2013 поддерживает подключение к Skype.</span><span class="sxs-lookup"><span data-stu-id="e696c-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="e696c-105">Благодаря этому пользователи Lync 2013 могут добавлять контакты Skype с помощью учетной записи Майкрософт пользователя Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="e696c-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="e696c-106">Клиенты Skype также могут добавлять пользователей Lync в свои списки контактов.</span><span class="sxs-lookup"><span data-stu-id="e696c-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="e696c-107">В соответствии с политиками, настроенными администратором в Lync Server, пользователи Lync и Skype могут обмениваться мгновенными сообщениями, просматривать сведения о присутствии друг друга и запускать голосовые и видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="e696c-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="e696c-108">Lync-Skype подключение также является компонентом Lync Online, и его можно включить для пользователей Lync Online в центре администрирования Lync в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e696c-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Microsoft 365 admin center.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="e696c-109">Если Lync Server уже настроен для подключения к Windows Messenger с помощью подключения к общедоступным службам обмена мгновенными сообщениями (PIC), то развертывание уже настроено для подключения к Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="e696c-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="e696c-110">Единственное изменение, которое вы можете подумать — переименовать существующую запись Messenger PIC как Skype.</span><span class="sxs-lookup"><span data-stu-id="e696c-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="e696c-111">Дополнительные сведения: Настройка параметров поставщика Skype PIC для Lync позже в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="e696c-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e696c-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="e696c-112">In This Section</span></span>

  - [<span data-ttu-id="e696c-113">Примечание о подключении к Lync-Skype в Lync Server 2013 для клиентов Lync Online</span><span class="sxs-lookup"><span data-stu-id="e696c-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="e696c-114">Доступ к сайту предоставления общедоступной службы обмена мгновенными сообщениями Lync Server с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e696c-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="e696c-115">Включение подключения к Lync-Skype в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e696c-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="e696c-116">Использование Lync-Skype подключения в Lync Server 2013 в качестве конечного пользователя</span><span class="sxs-lookup"><span data-stu-id="e696c-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="e696c-117">Вопросы и ответы: подготовка Lync Server 2013 для подключения к Skype</span><span class="sxs-lookup"><span data-stu-id="e696c-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

