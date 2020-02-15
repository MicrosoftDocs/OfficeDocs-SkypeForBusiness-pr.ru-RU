---
title: 'Lync Server 2013: Настройка политик для управления доступом федеративных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40b2a1fa071c7dd7f93e384418679ffcead38c0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="0fbef-102">Настройка политик для управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fbef-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fbef-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0fbef-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0fbef-104">При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="0fbef-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="0fbef-105">Можно настроить одну или несколько политик доступа внешних пользователей, чтобы управлять тем, могут ли пользователи федеративных доменов совместно работать с пользователями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0fbef-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="0fbef-106">Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="0fbef-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="0fbef-107">Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="0fbef-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="0fbef-108">Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="0fbef-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="0fbef-109">Это означает, что параметр политики ближе к объекту, на который влияет политика, чем больше влияет на объект.</span><span class="sxs-lookup"><span data-stu-id="0fbef-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0fbef-110">Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации.</span><span class="sxs-lookup"><span data-stu-id="0fbef-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="0fbef-111">Однако настроенные политики вступают в силу только при включении федерации для организации.</span><span class="sxs-lookup"><span data-stu-id="0fbef-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="0fbef-112">Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="0fbef-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="0fbef-113">Кроме того, если указать политику пользователя для управления доступом федеративного пользователя, политика применяется только к пользователям, для которых включена поддержка Lync Server 2013 и настроено на использование политики.</span><span class="sxs-lookup"><span data-stu-id="0fbef-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="0fbef-114">Чтобы настроить политику для поддержку доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="0fbef-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="0fbef-115">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0fbef-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0fbef-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0fbef-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0fbef-117">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0fbef-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0fbef-118">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0fbef-119">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0fbef-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="0fbef-120">Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей? щелкните глобальную политику, щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="0fbef-p104">Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="0fbef-p105">Чтобы создать новую политику пользователей, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Новая политика внешнего доступа** создайте уникальное имя в поле **Имя**, которое указывает, что охватывается политикой пользователей (например, **EnableFederatedUsers** для политики пользователей, которая разрешает связь с пользователями федеративных доменов).</span><span class="sxs-lookup"><span data-stu-id="0fbef-p105">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="0fbef-125">Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0fbef-126">(Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="0fbef-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0fbef-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="0fbef-128">Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="0fbef-129">Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="0fbef-130">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-130">Click **Commit**.</span></span>

<span data-ttu-id="0fbef-131">Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации.</span><span class="sxs-lookup"><span data-stu-id="0fbef-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="0fbef-132">Дополнительные сведения: [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="0fbef-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="0fbef-133">Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="0fbef-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="0fbef-134">Подробнее: [Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="0fbef-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="0fbef-135">Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="0fbef-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="0fbef-136">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0fbef-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0fbef-137">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0fbef-138">Введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0fbef-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="0fbef-139">Пример команды, которая задает глобальную политику для включения доступа федеративных пользователей, включения доступа из доменов XMPP, включения удаленного доступа пользователей, включения доступа из систем общедоступных поставщиков и предоставления возможности использовать аудио и видео при работе с поставщиками, обеспечивающими такую поддержку:</span><span class="sxs-lookup"><span data-stu-id="0fbef-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="0fbef-140">Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выбора в панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="0fbef-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="0fbef-141">Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="0fbef-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="0fbef-142">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0fbef-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0fbef-143">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0fbef-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0fbef-144">Введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0fbef-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="0fbef-145">Пример создания новой политики сайта:</span><span class="sxs-lookup"><span data-stu-id="0fbef-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="0fbef-146">Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="0fbef-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="0fbef-147">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0fbef-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0fbef-148">Введите следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0fbef-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="0fbef-p108">Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):</span><span class="sxs-lookup"><span data-stu-id="0fbef-p108">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="0fbef-151">Чтобы удалить политику сайта, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="0fbef-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="0fbef-152">Удаляет политику сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="0fbef-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="0fbef-153">Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0fbef-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0fbef-154">См. также</span><span class="sxs-lookup"><span data-stu-id="0fbef-154">See Also</span></span>


[<span data-ttu-id="0fbef-155">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fbef-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="0fbef-156">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fbef-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="0fbef-157">Управление федеративными доменами SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fbef-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="0fbef-158">Управление федеративными поставщиками SIP для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fbef-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="0fbef-159">Set — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0fbef-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="0fbef-160">New — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0fbef-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="0fbef-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0fbef-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="0fbef-162">Remove — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0fbef-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="0fbef-163">Granting — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0fbef-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

