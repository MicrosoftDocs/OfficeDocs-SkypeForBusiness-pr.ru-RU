---
title: 'Lync Server 2013: процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange'
description: 'Lync Server 2013: процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange.'
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
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542615"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="8c1dd-103">Процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c1dd-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c1dd-104">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="8c1dd-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="8c1dd-105">Для эффективного планирования интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange необходимо учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="8c1dd-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="8c1dd-106">Необходимые условия для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="8c1dd-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="8c1dd-107">обязательные этапы процесса интеграции.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="8c1dd-108">Необходимые компоненты развертывания для интеграции с размещаемой единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="8c1dd-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="8c1dd-109">Прежде чем начать процесс интеграции, необходимо предварительно развернуть Lync Server 2013 (как минимум, интерфейсный пул или сервер Standard Edition), пограничный сервер и клиенты Lync 2013 или Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="8c1dd-110">Процесс интеграции</span><span class="sxs-lookup"><span data-stu-id="8c1dd-110">Integration Process</span></span>

<span data-ttu-id="8c1dd-111">В следующей таблице приведен обзор процесса интеграции единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="8c1dd-112">Сведения о шагах развертывания приведены в статье [предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c1dd-113">Этап</span><span class="sxs-lookup"><span data-stu-id="8c1dd-113">Phase</span></span></th>
<th><span data-ttu-id="8c1dd-114">Действия</span><span class="sxs-lookup"><span data-stu-id="8c1dd-114">Steps</span></span></th>
<th><span data-ttu-id="8c1dd-115">Права и разрешения</span><span class="sxs-lookup"><span data-stu-id="8c1dd-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="8c1dd-116">Документация по развертыванию</span><span class="sxs-lookup"><span data-stu-id="8c1dd-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c1dd-117">Настройка пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c1dd-118">Настройка пограничного сервера для федерации.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="8c1dd-119">Ручное копирование данных на пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="8c1dd-120">Настройка поставщика услуг размещения на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c1dd-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8c1dd-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c1dd-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange</a></span><span class="sxs-lookup"><span data-stu-id="8c1dd-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c1dd-123">Настройка политики маршрутизации размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c1dd-124">Измените глобальную политику маршрутизации размещенной голосовой почты или создайте новую политику маршрутизации размещенной голосовой почты с областью "сайт" или "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="8c1dd-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="8c1dd-125">Для политик с областью "на пользователя" назначьте политику пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c1dd-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8c1dd-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c1dd-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Управление политиками размещенной голосовой почты в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c1dd-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c1dd-128">Включение поддержки размещаемой голосовой почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8c1dd-129">Настройте учетные записи для пользователей, почтовые ящики которых находятся в размещенной службе Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="8c1dd-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c1dd-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c1dd-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Предоставление пользователям размещенной голосовой почты в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c1dd-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c1dd-132">Настройка размещаемых контактных объектов.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="8c1dd-133">Создание контактных объектов для автосекретаря размещаемой единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="8c1dd-134">Создание контактных объектов для доступа подписчика размещаемой единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="8c1dd-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c1dd-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="8c1dd-136">Чтобы создать, изменить или удалить контактные объекты, пользователь, запускающий командлет New-CsExUmContact, Set-CsExUmContact или Remove-CsExUmContact, должен иметь соответствующее разрешение в подразделении Active Directory, где хранятся новые контактные объекты.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="8c1dd-137">Это разрешение можно предоставить, выполнив командлет Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="8c1dd-138">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c1dd-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="8c1dd-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Создание объектов Contact для размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="8c1dd-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

