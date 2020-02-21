---
title: 'Lync Server 2013: Настройка политик для управления удаленным доступом пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f1687a26e5bf464191b742d046bc28e8c8a329a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a><span data-ttu-id="9304a-102">Настройка политик для управления удаленным доступом пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9304a-102">Configure policies to control remote user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9304a-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9304a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9304a-104">Вы настраиваете одну или несколько политик доступа внешних пользователей, чтобы определять, могут ли удаленные пользователи совместно работать с внутренними пользователями Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9304a-104">You configure one or more external user access policies to control whether remote users can collaborate with internal Lync Server users.</span></span> <span data-ttu-id="9304a-105">Для управления доступом удаленных пользователей можно настраивать глобальные политики, а также политики уровня сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="9304a-105">To control remote user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="9304a-106">Политики уровня сайта переопределяют глобальную политику, а политики уровня пользователя переопределяют глобальную политику и политики уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="9304a-106">Site policies override the global policy, and user policies override site and global policies.</span></span> <span data-ttu-id="9304a-107">Дополнительные сведения о типах политик, которые можно настроить, приведены в статье [Управление федерациями и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9304a-107">For details about the types of policies that you can configure, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).</span></span> <span data-ttu-id="9304a-108">Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="9304a-108">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9304a-109">Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="9304a-109">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9304a-110">Это означает, что параметр политики ближе к объекту, на который влияет политика, чем больше влияет на объект.</span><span class="sxs-lookup"><span data-stu-id="9304a-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9304a-111">Политики для управления доступом пользователей можно настроить, даже если в организации не включен доступ удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9304a-111">You can configure policies to control remote user access, even if you have not enabled remote user access for your organization.</span></span> <span data-ttu-id="9304a-112">Однако настраиваемые политики будут действовать только при включении доступа удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9304a-112">However, the policies that you configure are in effect only when you have remote user access enabled for your organization.</span></span> <span data-ttu-id="9304a-113">Подробнее о включении удаленного доступа пользователей можно узнать <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">в статье Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9304a-113">For details about enabling remote user access, see <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Enable or disable federation and public IM connectivity in Lync Server 2013</A>.</span></span> <span data-ttu-id="9304a-114">Кроме того, если вы укажете политику пользователя для управления удаленным доступом пользователей, политика применяется только к пользователям, для которых включена Lync Server и настроено на использование политики.</span><span class="sxs-lookup"><span data-stu-id="9304a-114">Additionally, if you specify a user policy to control remote user access, the policy applies only to users that are enabled for Lync Server and configured to use the policy.</span></span> <span data-ttu-id="9304a-115">Дополнительные сведения об указании пользователей, которые могут входить на сервер Lync Server из удаленных расположений, приведены в статье <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9304a-115">For details about specifying users that can sign in to Lync Server from remote locations, see <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Assign an external user access policy to a Lync enabled user in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9304a-116">Используйте следующую процедуру для настройки каждой политики внешнего доступа, которую необходимо использовать для управления доступом удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9304a-116">Use the following procedure to configure each external access policy that you want to use to control remote user access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9304a-117">В этой процедуре описывается только настройка политики для включения взаимодействия с удаленными пользователями, однако каждая политика, настраиваемая для поддержки доступа удаленных пользователей, также может настраивать доступ федеративных пользователей и пользователей услуг общедоступного поставщика.</span><span class="sxs-lookup"><span data-stu-id="9304a-117">This procedure describes how to configure a policy only to enable communications with remote users, but each policy that you configure to support remote user access can also configure federated user access and public user access.</span></span> <span data-ttu-id="9304a-118">Дополнительные сведения о настройке политик для поддержки федеративных пользователей приведены <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">в статье Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9304a-118">For details about configuring policies to support federated users, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="9304a-119">Дополнительные сведения о настройке политик для поддержки открытых пользователей можно найти <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">в статье Создание или изменение общедоступных федеративных поставщиков SIP в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9304a-119">For details about configuring policies to support public users, see <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Create or edit public SIP federated providers in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a><span data-ttu-id="9304a-120">Настройка политики внешнего доступа для поддержки доступа удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="9304a-120">To configure an external access policy to support remote user access</span></span>

1.  <span data-ttu-id="9304a-121">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="9304a-121">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9304a-122">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9304a-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9304a-123">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9304a-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9304a-124">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="9304a-124">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="9304a-125">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9304a-125">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9304a-126">Чтобы настроить глобальную политику для поддержки доступа удаленных пользователей, щелкните глобальную политику, щелкните **Изменить** и **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="9304a-126">To configure the global policy to support remote user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="9304a-p105">Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9304a-p105">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="9304a-p106">Чтобы создать политику уровня пользователя, щелкните **Создать** и **Политика пользователя**. В разделе **Новая политика внешнего доступа** введите в поле **Имя** уникальное имя, которое показывает назначение политики (например, **EnableRemoteUsers** (Включить удаленных пользователей) для политики пользователя, которая включает взаимодействие с удаленными пользователями).</span><span class="sxs-lookup"><span data-stu-id="9304a-p106">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableRemoteUsers** for a user policy that enables communications for remote users).</span></span>
    
      - <span data-ttu-id="9304a-131">Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="9304a-131">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9304a-132">(Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.</span><span class="sxs-lookup"><span data-stu-id="9304a-132">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="9304a-133">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="9304a-133">Do one of the following:</span></span>
    
      - <span data-ttu-id="9304a-134">Чтобы включить для политики доступ удаленных пользователей, установите флажок **Разрешить взаимодействие с удаленными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="9304a-134">To enable remote user access for the policy, select the **Enable communications with remote users** check box.</span></span>
    
      - <span data-ttu-id="9304a-135">Чтобы отключить для политики доступ удаленных пользователей, снимите флажок **Разрешить взаимодействие с удаленными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="9304a-135">To disable remote user access for the policy, clear the **Enable communications with remote users** check box.</span></span>

7.  <span data-ttu-id="9304a-136">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9304a-136">Click **Commit**.</span></span>

<span data-ttu-id="9304a-137">Чтобы включить доступ удаленных пользователей, необходимо также включить поддержку доступа удаленных пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="9304a-137">To enable remote user access, you must also enable support for remote user access in your organization.</span></span> <span data-ttu-id="9304a-138">Дополнительные сведения: [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9304a-138">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="9304a-139">Если это политика уровня пользователя, необходимо также применить ее к пользователям, которые должны подключаться удаленно.</span><span class="sxs-lookup"><span data-stu-id="9304a-139">If this is a user policy, you must also apply the policy to users that you want to be able to connect remotely.</span></span> <span data-ttu-id="9304a-140">Дополнительные сведения приведены в статье [Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в среде Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="9304a-140">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) in the Deployment documentation or the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

