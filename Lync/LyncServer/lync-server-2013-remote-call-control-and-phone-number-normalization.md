---
title: 'Lync Server 2013: удаленное управление звонками и нормализация телефонных номеров'
description: 'Lync Server 2013: удаленное управление звонками и нормализация телефонных номеров.'
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
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555815"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="fa941-103">Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa941-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa941-104">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="fa941-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="fa941-105">Клиенты Lync загружают правила нормализации телефонных номеров в процессе загрузки файлов службы адресной книги (ABS).</span><span class="sxs-lookup"><span data-stu-id="fa941-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="fa941-106">В сценариях удаленного управления звонками правила нормализации телефонных номеров службы адресной книги применяются к входящим и исходящим вызовам контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="fa941-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="fa941-107">Для входящих вызовов пользователя с поддержкой контроля допуска звонков номер телефона вызывающего абонента сначала нормализуется в формате E.164 с помощью шлюза SIP/CSTA или УАТС.</span><span class="sxs-lookup"><span data-stu-id="fa941-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="fa941-108">Когда Lync Server 2013 Получает вызов от шлюза, он выполняет обратный просмотр номера (RNL) на номере телефона абонента со нормализованным числом в списке контактов Microsoft Office Outlook или глобальном списке адресов, который хранится в службе адресной книги.</span><span class="sxs-lookup"><span data-stu-id="fa941-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="fa941-109">Если при обратном поиске номера успешно получено совпадение, вызывающий абонент идентифицируется по имени в уведомлении о входящем вызове.</span><span class="sxs-lookup"><span data-stu-id="fa941-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="fa941-110">Для исходящих звонков по удаленному управлению звонками Lync применяет правила нормализации номера телефона службы адресной книги к набранному номеру перед маршрутизацией вызова в шлюз SIP/CSTA.</span><span class="sxs-lookup"><span data-stu-id="fa941-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="fa941-111">Сведения о создании правил нормализации телефонных номеров для удаленного управления звонками приведены в документации по планированию для [абонентских планов и правил нормализации в Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) .</span><span class="sxs-lookup"><span data-stu-id="fa941-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="fa941-112">Перенос правил нормализации телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="fa941-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="fa941-113">При переносе пользователей, для которых ранее было разрешено удаленное управление звонками, изучите следующие разделы документации по миграции:</span><span class="sxs-lookup"><span data-stu-id="fa941-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="fa941-114">В случае Lync Server 2010 вы найдете в статье Migration [Address Book (миграция адресной книги](migrate-address-book.md) ) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="fa941-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="fa941-115">Сведения о Communications Server 2007 R2 приведены в статье [Миграция адресной книги](migrate-address-book.md) в документации по миграции.</span><span class="sxs-lookup"><span data-stu-id="fa941-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

