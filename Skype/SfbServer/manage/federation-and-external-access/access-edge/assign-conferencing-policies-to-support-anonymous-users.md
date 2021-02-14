---
title: Назначение политик для поддержки анонимных пользователей
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Администратор управляет, кто может приглашать анонимных пользователей, путем настройки политики конференц-связи для поддержки анонимных пользователей и применения этой политики конференц-связи к определенным пользователям.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817459"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="fad7a-103">Назначение политик для поддержки анонимных пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fad7a-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="fad7a-104">По умолчанию все пользователи не могут пригласить анонимных пользователей для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="fad7a-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="fad7a-105">Администратор управляет, кто может приглашать анонимных пользователей, путем настройки политики конференц-связи для поддержки анонимных пользователей и применения этой политики конференц-связи к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="fad7a-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="fad7a-106">Дополнительные сведения о настройке политик для поддержки анонимных пользователей см. в дополнительных сведениях о создании политик в Skype для бизнеса [Server](../../conferencing/create-policies.md) и управлении федерацией и внешним доступом к Skype для бизнеса [Server.](../managing-federation-and-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="fad7a-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="fad7a-107">Используйте процедуру в этом разделе для применения уже созданной политики конференц-связи к одному или нескольким пользователям, а также к группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="fad7a-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="fad7a-108">В дополнение к настройке и применению политики для разрешения пользователям приглашать анонимных пользователей необходимо также обеспечивать поддержку анонимных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="fad7a-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="fad7a-109">For details, see [Configure policies to control public user access in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="fad7a-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="fad7a-110">Чтобы настроить политику пользователей для анонимного участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="fad7a-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="fad7a-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="fad7a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fad7a-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fad7a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fad7a-113">На левой панели навигации щелкните **Конференц-связь**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fad7a-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="fad7a-p103">Чтобы создать новую политику пользователей, щелкните **Создать**, затем щелкните **Политика сайта**. Создайте уникальное имя в поле **Имя**, которое указывает, что охватывается политикой пользователей (например, **EnableAnonymous** для политики пользователей, которая разрешает связь с анонимными пользователями).</span><span class="sxs-lookup"><span data-stu-id="fad7a-p103">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="fad7a-116">Чтобы настроить существующую политику пользователей, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="fad7a-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="fad7a-117">В диалоговом окне **Политики конференц-связи** установите флажок **Разрешить участникам приглашать анонимных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="fad7a-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="fad7a-118">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fad7a-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="fad7a-119">В левой панели навигации щелкните **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="fad7a-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="fad7a-120">В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="fad7a-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="fad7a-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span><span class="sxs-lookup"><span data-stu-id="fad7a-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="fad7a-122"><STRONG> &lt; Автоматические &gt; </STRONG> параметры применяют параметры установки сервера по умолчанию и автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="fad7a-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="fad7a-123">Чтобы разрешить пользователям приглашать анонимных пользователей в конференции, необходимо также включить поддержку анонимных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="fad7a-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="fad7a-124">For details, see [Configure policies to control public user access in Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="fad7a-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

