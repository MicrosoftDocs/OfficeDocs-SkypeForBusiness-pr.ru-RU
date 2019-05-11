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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно контролировать, кто может приглашать анонимных пользователей, настроив политики конференц-связи для поддержки анонимных пользователей и применение политики конференц-связи к определенным пользователям.
ms.openlocfilehash: afb107f7f3d91d634e5adaef4b9d0a2fbc1ee298
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919537"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="22801-103">Назначение политики конференц-связи для поддержки анонимных пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="22801-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="22801-104">По умолчанию все пользователи не могут приглашать анонимных пользователей для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="22801-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="22801-105">Можно контролировать, кто может приглашать анонимных пользователей, настроив политики конференц-связи для поддержки анонимных пользователей и применение политики конференц-связи к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="22801-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="22801-106">Для получения дополнительных сведений о настройке политик конференц-связи для поддержки анонимных пользователей видеть [Создание политики конференц-связи в Скайп для Business Server](../../conferencing/create-policies.md) и [Управление Федерация и внешний доступ к Скайп для Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="22801-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="22801-107">Используйте описанную в этом разделе для применения политики конференц-связи, который уже создан для одного или нескольких пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="22801-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="22801-108">В дополнение к настройке и применению политики, чтобы разрешить пользователям приглашать анонимных пользователей, необходимо также включить поддержку для анонимных пользователей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="22801-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="22801-109">Дополнительные сведения см [Настройка политик для управления доступом пользователей общедоступных служб в Скайп для Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="22801-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="22801-110">Чтобы настроить политику пользователей для анонимного участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="22801-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="22801-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22801-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22801-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="22801-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="22801-113">В левой панели навигации щелкните **конференц-связь**и затем выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="22801-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="22801-114">Чтобы создать новую политику пользователя, нажмите кнопку **Создать**и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="22801-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="22801-115">Задайте уникальное имя в поле **имя** , которое указывает, рассматривается политики пользователя (например, **EnableAnonymous** для политики пользователя, которая включает взаимодействие с анонимными пользователями).</span><span class="sxs-lookup"><span data-stu-id="22801-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="22801-116">Чтобы настроить существующую политику, выберите соответствующую политику, перечисленных в таблице, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="22801-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="22801-117">В диалоговом окне **Политики конференц-связи** установите флажок **Разрешить участникам приглашать анонимных пользователей** .</span><span class="sxs-lookup"><span data-stu-id="22801-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="22801-118">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="22801-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="22801-119">В левой панели навигации щелкните **Пользователи**и выполните поиск учетной записи пользователя, которую требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="22801-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="22801-120">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="22801-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="22801-121">В **Скайп изменение для пользователя Business Server** в разделе **Политика конференц-связи**выберите политику пользователей с настройкой доступа анонимных пользователей, который будет использоваться для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="22801-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="22801-122"><STRONG> &lt;Автоматического&gt; </STRONG> параметры применяются параметры установки сервера по умолчанию и автоматически применяются на сервере.</span><span class="sxs-lookup"><span data-stu-id="22801-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="22801-123">Чтобы разрешить пользователям приглашать анонимных пользователей к конференциям, необходимо также включить поддержку для анонимных пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="22801-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="22801-124">Дополнительные сведения см [Настройка политик для управления доступом пользователей общедоступных служб в Скайп для Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="22801-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

