---
title: 'Lync Server 2013: удаленное управление звонками и нормализация телефонных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="831bf-102">Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="831bf-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="831bf-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="831bf-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="831bf-104">Клиенты Lync загружают правила нормализации номера телефона в рамках скачивания файла службы адресной книги (ABS).</span><span class="sxs-lookup"><span data-stu-id="831bf-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="831bf-105">В сценариях удаленного управления звонками правила нормализации номера телефонной книги применяются к входящим и исходящим звонкам удаленного управления звонками.</span><span class="sxs-lookup"><span data-stu-id="831bf-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="831bf-106">Для входящих звонков с удаленным пользователем, поддерживающим управление звонками, номер телефона, используемый для вызывающего абонента, сначала нормализован на формат E. 164 либо с помощью шлюза SIP/КСТА, либо из частной сети обмена филиалами (УАТС).</span><span class="sxs-lookup"><span data-stu-id="831bf-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="831bf-107">Когда Lync Server 2013 получает звонок от шлюза, он выполняет обратный просмотр номера (РНЛ) на номере телефона вызывающего абонента со стандартным номером в списке контактов Microsoft Office Outlook или глобальном списке адресов (GAL), который хранится в Служба адресной книги.</span><span class="sxs-lookup"><span data-stu-id="831bf-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="831bf-108">Если обратный поиск номеров успешно находит совпадение, вызывающий объект определяется по имени в уведомлении о входящем звонке.</span><span class="sxs-lookup"><span data-stu-id="831bf-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="831bf-109">Для исходящих вызовов удаленного управления звонками Lync применяет правила нормализации номера телефона службы адресной книги к набору номера перед тем, как перенаправить звонок на шлюз SIP/КСТА.</span><span class="sxs-lookup"><span data-stu-id="831bf-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="831bf-110">Дополнительные сведения о создании правил нормализации номера телефона для удаленного управления звонками можно найти [в разделе планы и правила нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="831bf-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="831bf-111">Миграция правил нормализации номера телефона</span><span class="sxs-lookup"><span data-stu-id="831bf-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="831bf-112">Если вы переносите пользователей, для которых уже разрешено удаленное управление звонками, ознакомьтесь со следующими разделами в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="831bf-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="831bf-113">Для Lync Server 2010 — в разделе [Миграция адресной книги](migrate-address-book.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="831bf-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="831bf-114">Сервер Communications Server 2007 R2 можно найти в разделе [Миграция адресной книги](migrate-address-book_1.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="831bf-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

