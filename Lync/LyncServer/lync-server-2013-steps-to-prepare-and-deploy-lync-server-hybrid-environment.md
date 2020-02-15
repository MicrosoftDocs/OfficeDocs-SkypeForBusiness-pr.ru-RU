---
title: 'Lync Server 2013: действия по подготовке и развертыванию гибридной среды Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3326db7ce62279c4295bc13ec262a5a553ca5e62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="2c376-102">Действия по подготовке и развертыванию гибридной среды Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c376-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c376-103">_**Последнее изменение темы:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="2c376-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="2c376-104">В следующей таблице приведены действия, необходимые для подготовки среды к гибридному развертыванию со Skype для бизнеса Online и Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c376-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c376-105">Выполнено?</span><span class="sxs-lookup"><span data-stu-id="2c376-105">Completed?</span></span></th>
<th><span data-ttu-id="2c376-106">Шаг</span><span class="sxs-lookup"><span data-stu-id="2c376-106">Step</span></span></th>
<th><span data-ttu-id="2c376-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2c376-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2c376-108">Создание учетной записи клиента для Office 365 и включение Lync Online</span><span class="sxs-lookup"><span data-stu-id="2c376-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="2c376-109">Узнайте о Office 365 и Lync Online в <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="2c376-110">Чтобы убедиться, что ваша среда готова к работе с Office 365, ознакомьтесь с <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">требованиями к системе</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="2c376-111">Подробнее о настройке Office 365 вы найдете в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Начало работы с office 365</a> и <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Настройка Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="http://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2c376-112">Добавление домена и проверка прав на владение доменом</span><span class="sxs-lookup"><span data-stu-id="2c376-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="2c376-113">Домен иногда также называется <em>доменом запоминающийся</em>.</span><span class="sxs-lookup"><span data-stu-id="2c376-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="2c376-114">Вам необходимо добавить домен в клиент Office 365 и затем проверить домен в Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c376-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="2c376-115">Эти действия предназначены для проверки прав владения доменом.</span><span class="sxs-lookup"><span data-stu-id="2c376-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="2c376-116">Чтобы добавить свой домен в клиент Office 365, выполните действия, описанные в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Добавление домена в office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="2c376-117">Выполните все действия, описанные в разделах этой статьи, в том &quot;числе изменение записей DNS для служб Office 365.&quot;</span><span class="sxs-lookup"><span data-stu-id="2c376-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2c376-118">Проверка готовности среды</span><span class="sxs-lookup"><span data-stu-id="2c376-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="2c376-119">С помощью помощника по установке Office 365 вы можете развернуть Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c376-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="2c376-120">Дополнительные сведения см. <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">в статье Использование помощника по настройке для определения готовности Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="2c376-121">Дополнительные сведения об использовании этого средства и развертывании Office 365 содержатся в <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">руководстве по развертыванию office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2c376-122">Подготовка к синхронизации Active Directory</span><span class="sxs-lookup"><span data-stu-id="2c376-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="2c376-123">Синхронизация Active Directory обеспечивает непрерывную синхронизацию локальной службы каталогов Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c376-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="2c376-124">Это позволяет создавать синхронизированные версии каждой учетной записи пользователя и группы, а также выполнять синхронизацию глобального списка адресов (GAL) из локальной среды Microsoft Exchange Server в Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2c376-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2c376-125">Необходимо синхронизировать учетные записи AD для всех пользователей Lync в Организации между локальными и подключенными развертываниями Lync, даже если пользователи не перемещены в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2c376-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="2c376-126">Если вы не синхронизируете всех пользователей, связь между локальными и сетевыми пользователями в Организации может работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="2c376-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="2c376-127">Чтобы подготовить среду к синхронизации Active Directory, выполните действия, описанные в статье <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">схема синхронизации службы каталогов</a>, в том числе Настройка единого входа.</span><span class="sxs-lookup"><span data-stu-id="2c376-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2c376-128">Создание сертификатов для служб федерации Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="2c376-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="2c376-129">Вам потребуется создать сертификаты, используемые для федерации удостоверений Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c376-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="2c376-130">Для получения дополнительных сведений обратитесь к разделу "сертификаты сервера федерации" плана for Active Directory для использования с одним входным разделом в разделе <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Контрольный список: использование AD FS для реализации единого входа и управления им</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2c376-131">Назначение сертификатов Active Directory</span><span class="sxs-lookup"><span data-stu-id="2c376-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="2c376-132">После создания сертификатов, используемых для федерации удостоверений с Office 365, необходимо установить и назначить их.</span><span class="sxs-lookup"><span data-stu-id="2c376-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="2c376-133">Перемещение пилотных пользователей в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2c376-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="2c376-134">После выполнения действий по подготовке и настройке среды для Skype для бизнеса Online можно начать перемещение пилотных пользователей в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="2c376-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="2c376-135">Ознакомьтесь <a href="lync-server-2013-move-users-to-lync-online.md">со статьей перемещение пользователей в Lync Online в Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="2c376-136">Администрирование пользователей в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="2c376-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="2c376-137">Сведения о том, как администрировать пользователей в гибридном развертывании, приведены <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">в разделе Администрирование пользователей в гибридном развертывании Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2c376-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

