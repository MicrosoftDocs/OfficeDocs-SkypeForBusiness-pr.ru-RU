---
title: 'Lync Server 2013: поддержка единой системы обмена сообщениями Exchange (единой системы обмена сообщениями)'
description: 'Lync Server 2013: поддержка единой системы обмена сообщениями Exchange (единой системы обмена сообщениями).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 563517bb72167bbab0b08eba3b1359ae3ab52836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564805"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a><span data-ttu-id="7b713-103">Поддержка единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b713-103">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b713-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7b713-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7b713-105">Lync Server 2013 поддерживает интеграцию с единой системой обмена сообщениями Exchange для объединения голосовых сообщений и сообщений электронной почты в единую инфраструктуру обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7b713-105">Lync Server 2013 supports integration with Exchange Unified Messaging (UM) for combining voice messaging and email messaging into a single messaging infrastructure.</span></span> <span data-ttu-id="7b713-106">В Exchange 2013 единая система обмена сообщениями Exchange состоит из службы единой системы обмена сообщениями Exchange, которая устанавливается и запускается на сервере почтовых ящиков, а также на маршрутизаторе вызовов единой системы обмена сообщениями, установленном и работающем на сервере клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="7b713-106">In Exchange 2013, Exchange UM consists of the Exchange UM service, which is installed and runs on the Mailbox server, and the UM Call Router, which is installed and runs on the Client Access server.</span></span> <span data-ttu-id="7b713-107">Для развертываний корпоративной голосовой связи в Lync Server 2013 система обмена сообщениями Exchange объединяет обмен голосовыми сообщениями и электронную почту в едином хранилище, доступном с телефона (то есть с помощью голосового доступа к Outlook) или компьютера.</span><span class="sxs-lookup"><span data-stu-id="7b713-107">For Lync Server 2013 Enterprise Voice deployments, Exchange UM combines voice messaging and email messaging into a single store that is accessible from a telephone (that is, Outlook Voice Access) or a computer.</span></span> <span data-ttu-id="7b713-108">Единая система обмена сообщениями Exchange и Lync Server 2013 взаимодействуют для предоставления автоответчика, голосового доступа к Outlook и служб автосекретаря для пользователей корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7b713-108">Exchange UM and Lync Server 2013 work together to provide call answering, Outlook Voice Access, and auto attendant services to users of Enterprise Voice.</span></span>

<span data-ttu-id="7b713-109">Помимо поддержки интеграции с локальными развертываниями единой системы обмена сообщениями Exchange, Lync Server 2013 поддерживает интеграцию с размещенной единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="7b713-109">In addition to the support for integration with on-premises deployments of Exchange UM, Lync Server 2013 supports integration with hosted Exchange UM.</span></span> <span data-ttu-id="7b713-110">Это позволяет вам предоставлять возможность обмена голосовыми сообщениями пользователям, если вы выполните миграцию некоторых из них или их всех на поставщика размещенной службы Exchange, такого как Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b713-110">This enables you to provide voice messaging to your users if you migrate some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="7b713-111">Lync Server 2013 поддерживает следующие версии:</span><span class="sxs-lookup"><span data-stu-id="7b713-111">Lync Server 2013 supports the following versions:</span></span>

  - <span data-ttu-id="7b713-112">Microsoft Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="7b713-112">Microsoft Exchange 2013</span></span>

  - <span data-ttu-id="7b713-113">Microsoft Exchange Server 2010 (обязательно) или с последним пакетом обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="7b713-113">Microsoft Exchange Server 2010 (required) or with latest service pack (recommended)</span></span>

  - <span data-ttu-id="7b713-114">Microsoft Exchange Server 2007 с пакетом обновления 1 (SP1) (обязательно) или последним пакетом обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="7b713-114">Microsoft Exchange Server 2007 with Service Pack 1 (SP1) (required) or latest service pack (recommended)</span></span>

<span data-ttu-id="7b713-115">Совместное размещение единой системы обмена сообщениями Exchange с Lync Server 2013 или Lync Server 2013 невозможно.</span><span class="sxs-lookup"><span data-stu-id="7b713-115">You cannot collocate Exchange UM with Lync Server 2013 or a Lync Server 2013 database.</span></span> <span data-ttu-id="7b713-116">Вы можете установить Exchange единой системы обмена сообщениями и Lync Server 2013 в отдельные леса.</span><span class="sxs-lookup"><span data-stu-id="7b713-116">You can install Exchange UM and Lync Server 2013 in separate forests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b713-117">Единая система обмена сообщениями Exchange может не потребоваться для развертываний корпоративной голосовой связи с развернутой УАТС, так как УАТС может продолжать предоставлять доступ к голосовой почте и связанным службам всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="7b713-117">Exchange UM may not be required for Enterprise Voice deployments that have a PBX deployed, because the PBX can continue to provide voice mail and related services to all users.</span></span> <span data-ttu-id="7b713-118">При окончательном отключении УАТС (например, при развертывании магистральной магистрали SIP для подключения к телефонной сети общего пользования) необходимо перенастроить единую систему обмена сообщениями Exchange для предоставления голосовой почты пользователям, которые ранее использовали систему голосовой почты УАТС.</span><span class="sxs-lookup"><span data-stu-id="7b713-118">If you eventually retire the PBX (for example, if you deploy SIP trunking for public switched telephone network (PSTN) connectivity), you must reconfigure Exchange UM to provide voice mail to users who previously used the PBX voice mail system.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b713-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="7b713-119">In This Section</span></span>

  - [<span data-ttu-id="7b713-120">Компоненты и топологии для локальной единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b713-120">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [<span data-ttu-id="7b713-121">Поддержка интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b713-121">Support for hosted Exchange UM integration in Lync Server 2013</span></span>](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

