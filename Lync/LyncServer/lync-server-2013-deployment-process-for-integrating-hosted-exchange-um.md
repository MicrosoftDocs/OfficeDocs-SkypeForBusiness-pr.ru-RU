---
title: 'Lync Server 2013: процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ae12ee384a78acd8c5c390715b05791b7a0df8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522596"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="d5d5b-102">Процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5d5b-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d5b-103">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="d5d5b-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="d5d5b-104">Для эффективного планирования интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange необходимо учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="d5d5b-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="d5d5b-105">Необходимые условия для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="d5d5b-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="d5d5b-106">обязательные этапы процесса интеграции.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="d5d5b-107">Необходимые компоненты развертывания для интеграции с размещаемой единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="d5d5b-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="d5d5b-108">Прежде чем начать процесс интеграции, необходимо предварительно развернуть Lync Server 2013 (как минимум, интерфейсный пул или сервер Standard Edition), пограничный сервер и клиенты Lync 2013 или Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="d5d5b-109">Процесс интеграции</span><span class="sxs-lookup"><span data-stu-id="d5d5b-109">Integration Process</span></span>

<span data-ttu-id="d5d5b-110">В следующей таблице приведен обзор процесса интеграции единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="d5d5b-111">Сведения о шагах развертывания приведены в статье [предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5d5b-112">Этап</span><span class="sxs-lookup"><span data-stu-id="d5d5b-112">Phase</span></span></th>
<th><span data-ttu-id="d5d5b-113">Действия</span><span class="sxs-lookup"><span data-stu-id="d5d5b-113">Steps</span></span></th>
<th><span data-ttu-id="d5d5b-114">Права и разрешения</span><span class="sxs-lookup"><span data-stu-id="d5d5b-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="d5d5b-115">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="d5d5b-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5d5b-116">Настройка пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d5d5b-117">Настройка пограничного сервера для федерации.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="d5d5b-118">Ручное копирование данных на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d5d5b-119">Настройка поставщика услуг размещения на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d5d5b-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5d5b-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d5d5b-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange</a></span><span class="sxs-lookup"><span data-stu-id="d5d5b-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d5b-122">Настройка политики маршрутизации размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d5d5b-123">Измените глобальную политику маршрутизации размещенной голосовой почты или создайте новую политику маршрутизации размещенной голосовой почты с областью "сайт" или "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="d5d5b-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="d5d5b-124">Для политик с областью "на пользователя" назначьте политику пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d5d5b-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5d5b-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d5d5b-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Управление политиками размещенной голосовой почты в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d5d5b-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5d5b-127">Включение поддержки размещаемой голосовой почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d5d5b-128">Настройте учетные записи для пользователей, почтовые ящики которых находятся в размещенной службе Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d5d5b-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d5d5b-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d5d5b-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Предоставление пользователям размещенной голосовой почты в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d5d5b-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5d5b-131">Настройка размещаемых контактных объектов.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d5d5b-132">Создание контактных объектов для автосекретаря размещаемой единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="d5d5b-133">Создание контактных объектов для доступа подписчика размещаемой единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d5d5b-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d5d5b-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d5d5b-135">Чтобы создать, изменить или удалить контактные объекты, пользователь, запускающий командлет New-CsExUmContact, Set-CsExUmContact или Remove-CsExUmContact, должен иметь соответствующее разрешение в подразделении Active Directory, где хранятся новые контактные объекты.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="d5d5b-136">Это разрешение можно предоставить, выполнив командлет Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="d5d5b-137">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d5d5b-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="d5d5b-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d5d5b-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

