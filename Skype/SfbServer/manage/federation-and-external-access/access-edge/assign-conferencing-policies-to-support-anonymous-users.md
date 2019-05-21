---
title: Назначение политик конференции для поддержки анонимных пользователей
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете управлять тем, кто может приглашать анонимных пользователей, настроив политику конференций для поддержки анонимных пользователей и применяя эту политику конференций к определенным пользователям.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280287"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="f50dd-103">Назначение политик конференций для поддержки анонимных пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f50dd-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="f50dd-104">По умолчанию всем пользователям запрещено приглашать анонимных пользователей для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="f50dd-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="f50dd-105">Вы можете управлять тем, кто может приглашать анонимных пользователей, настроив политику конференций для поддержки анонимных пользователей и применяя эту политику конференций к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="f50dd-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="f50dd-106">Сведения о настройке политик конференц-связи для поддержки анонимных пользователей можно найти [в разделе Создание политик конференц-связи в Skype для бизнеса Server](../../conferencing/create-policies.md) и [Управление интеграцией и внешним доступом к Skype для бизнеса Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="f50dd-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="f50dd-107">В этом разделе описана процедура применения политики конференц-связи, уже созданной для одного или нескольких пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="f50dd-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="f50dd-108">Помимо настройки и применения политики для предоставления пользователям возможности приглашать анонимных пользователей, необходимо также включить поддержку анонимных пользователей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f50dd-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="f50dd-109">Подробности можно найти [в разделе Настройка политик для управления доступом пользователей в Skype для бизнеса Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f50dd-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="f50dd-110">Настройка политики пользователя для анонимного участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="f50dd-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="f50dd-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f50dd-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f50dd-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f50dd-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f50dd-113">На панели навигации слева выберите **Конференц**-связь, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f50dd-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="f50dd-114">Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="f50dd-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="f50dd-115">Создайте уникальное имя в поле **Name (имя** ), которое указывает политику пользователя (например, **енаблеанонимаус** для политики пользователя, которая включает связь с анонимными пользователями).</span><span class="sxs-lookup"><span data-stu-id="f50dd-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="f50dd-116">Чтобы настроить существующую политику пользователей, щелкните соответствующую политику, указанную в таблице, и выберите команду **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f50dd-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="f50dd-117">В диалоговом окне **политики Конференц** -связи установите флажок **Разрешить участникам приглашать анонимных пользователей** .</span><span class="sxs-lookup"><span data-stu-id="f50dd-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="f50dd-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f50dd-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="f50dd-119">На панели навигации слева выберите пункт **Пользователи**, а затем выполните поиск по учетной записи пользователя, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="f50dd-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="f50dd-120">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="f50dd-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="f50dd-121">В диалоговом окне **изменение пользователя сервера Skype для бизнеса Server** в разделе **Политика Конференц**-связи выберите политику пользователей с конфигурацией "анонимный доступ", которую вы хотите применить для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f50dd-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="f50dd-122">Параметры <STRONG> &lt;автоматической&gt; </STRONG> настройки применяются к параметрам установки сервера по умолчанию и автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="f50dd-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="f50dd-123">Чтобы разрешить пользователям приглашать анонимных пользователей на Конференции, необходимо также включить поддержку анонимных пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="f50dd-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="f50dd-124">Подробности можно найти [в разделе Настройка политик для управления доступом пользователей в Skype для бизнеса Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f50dd-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

