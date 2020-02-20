---
title: 'Lync Server 2013: назначение политик конференц-связи для поддержки анонимных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4aaa2ee1f6734059983720ca9c3e228ab561a4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="7795e-102">Назначение политик конференц-связи для поддержки анонимных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7795e-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7795e-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7795e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7795e-104">По умолчанию все пользователи не могут пригласить анонимных пользователей для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="7795e-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="7795e-105">Администратор управляет, кто может приглашать анонимных пользователей, путем настройки политики конференц-связи для поддержки анонимных пользователей и применения этой политики конференц-связи к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="7795e-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="7795e-106">Дополнительные сведения о настройке политик конференц-связи для поддержки анонимных пользователей можно узнать [в статье Создание или изменение политики конференц-связи в Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) и [Управление Федерации и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="7795e-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="7795e-107">Используйте процедуру в этом разделе для применения уже созданной политики конференц-связи к одному или нескольким пользователям, а также к группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="7795e-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7795e-108">В дополнение к настройке и применению политики для разрешения пользователям приглашать анонимных пользователей необходимо также обеспечивать поддержку анонимных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7795e-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="7795e-109">Подробнее: <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Настройка политик для управления доступом пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7795e-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="7795e-110">Чтобы настроить политику пользователей для анонимного участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="7795e-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="7795e-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7795e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7795e-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7795e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7795e-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7795e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7795e-114">На левой панели навигации щелкните **Конференц-связь**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7795e-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="7795e-p104">Чтобы создать новую политику пользователей, щелкните **Создать**, затем щелкните **Политика сайта**. Создайте уникальное имя в поле **Имя**, которое указывает, что охватывается политикой пользователей (например, **EnableAnonymous** для политики пользователей, которая разрешает связь с анонимными пользователями).</span><span class="sxs-lookup"><span data-stu-id="7795e-p104">To create a new user policy, click **New**, and then click **User policy**. Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="7795e-117">Чтобы настроить существующую политику пользователей, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="7795e-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="7795e-118">В диалоговом окне **Политики конференц-связи** установите флажок **Разрешить участникам приглашать анонимных пользователей**.</span><span class="sxs-lookup"><span data-stu-id="7795e-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="7795e-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7795e-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="7795e-120">В левой панели навигации щелкните **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="7795e-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="7795e-121">В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="7795e-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="7795e-122">В окне **Изменение пользователя Lync Server** перейдите в раздел **Политика конференц-связи** и выберите политику пользователей с настройкой доступа анонимных пользователей, которую следует применить к данному пользователю.</span><span class="sxs-lookup"><span data-stu-id="7795e-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7795e-123">Автоматические параметры применяются к параметрам установки сервера по умолчанию и автоматически применяются сервером. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="7795e-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="7795e-124">Чтобы разрешить пользователям приглашать анонимных пользователей в конференции, необходимо также включить поддержку анонимных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="7795e-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="7795e-125">Дополнительные сведения: [Настройка политик для управления доступом пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="7795e-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

