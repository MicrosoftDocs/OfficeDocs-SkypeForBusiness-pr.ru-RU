---
title: 'Lync Server 2013: назначение политик конференции для поддержки анонимных пользователей'
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
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a><span data-ttu-id="22ea3-102">Назначение политик конференции для поддержки анонимных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22ea3-102">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22ea3-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="22ea3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="22ea3-104">По умолчанию всем пользователям запрещено приглашать анонимных пользователей для участия в собрании.</span><span class="sxs-lookup"><span data-stu-id="22ea3-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="22ea3-105">Вы можете управлять тем, кто может приглашать анонимных пользователей, настроив политику конференций для поддержки анонимных пользователей и применяя эту политику конференций к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="22ea3-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="22ea3-106">Дополнительные сведения о настройке политик конференц-связи для поддержки анонимных пользователей можно найти [в разделе Создание или изменение политики конференц-связи в Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) и [Управление интеграцией и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="22ea3-106">For details about how to configure a conferencing policies to support anonymous users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) and [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span>

<span data-ttu-id="22ea3-107">В этом разделе описана процедура применения политики конференц-связи, уже созданной для одного или нескольких пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="22ea3-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22ea3-108">Помимо настройки и применения политики для предоставления пользователям возможности приглашать анонимных пользователей, необходимо также включить поддержку анонимных пользователей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="22ea3-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="22ea3-109">Подробности можно найти <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">в разделе Настройка политик для доступа пользователей Public в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="22ea3-109">For details, see <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configure policies to control public user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="22ea3-110">Настройка политики пользователя для анонимного участия в собраниях</span><span class="sxs-lookup"><span data-stu-id="22ea3-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="22ea3-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22ea3-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22ea3-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22ea3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22ea3-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22ea3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22ea3-114">На панели навигации слева выберите **Конференц**-связь, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="22ea3-114">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="22ea3-115">Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="22ea3-115">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="22ea3-116">Создайте уникальное имя в поле **Name (имя** ), которое указывает политику пользователя (например, **енаблеанонимаус** для политики пользователя, которая включает связь с анонимными пользователями).</span><span class="sxs-lookup"><span data-stu-id="22ea3-116">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="22ea3-117">Чтобы настроить существующую политику пользователей, щелкните соответствующую политику, указанную в таблице, и выберите команду **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="22ea3-117">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="22ea3-118">В диалоговом окне **политики Конференц** -связи установите флажок **Разрешить участникам приглашать анонимных пользователей** .</span><span class="sxs-lookup"><span data-stu-id="22ea3-118">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="22ea3-119">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="22ea3-119">Click **Commit**.</span></span>

6.  <span data-ttu-id="22ea3-120">На панели навигации слева выберите пункт **Пользователи**, а затем выполните поиск по учетной записи пользователя, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="22ea3-120">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="22ea3-121">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="22ea3-121">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="22ea3-122">В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика Конференц**-связи выберите политику пользователей с конфигурацией "анонимный доступ", которую вы хотите применить для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="22ea3-122">In **Edit Lync Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22ea3-123">Параметры <STRONG> &lt;автоматической&gt; </STRONG> настройки применяются к параметрам установки сервера по умолчанию и автоматически применяются сервером.</span><span class="sxs-lookup"><span data-stu-id="22ea3-123">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>

    
    </div>

<span data-ttu-id="22ea3-124">Чтобы разрешить пользователям приглашать анонимных пользователей на Конференции, необходимо также включить поддержку анонимных пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="22ea3-124">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="22ea3-125">Подробности можно найти в разделе [Настройка политик для управления доступом пользователей в Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="22ea3-125">For details, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

