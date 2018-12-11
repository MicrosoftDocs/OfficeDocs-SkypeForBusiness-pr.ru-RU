---
title: Настройка политик управления доступом федеративных пользователей
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'При настройке политик для поддержки обмена данными с федеративным партнерам политики применяются для пользователей из федеративных доменов. '
ms.openlocfilehash: fcb4b0651c81316e06ab659430c3b0e9e5664e64
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222991"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="384c3-103">Настройка политик для управления доступом федеративных пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="384c3-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="384c3-104">При настройке политик для поддержки обмена данными с федеративным партнерам политики применяются для пользователей из федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="384c3-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="384c3-105">Можно настроить один или несколько политик доступа внешних пользователей для управления ли пользователей из федеративных доменов можно совместно работать с вашей Скайп для пользователей Business Server.</span><span class="sxs-lookup"><span data-stu-id="384c3-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="384c3-106">Для управления доступом федеративных пользователей, можно настроить политики на глобальном, сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="384c3-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="384c3-107">Скайп Business Server параметры политики, применяемые на одном уровне политики можно переопределить параметры, которые применяются на уровне другой политики.</span><span class="sxs-lookup"><span data-stu-id="384c3-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="384c3-108">— Это Скайп для определения приоритета Business Server: политика пользователя (большинство влияют на то) переопределяет политики сайта, а затем политика сайта переопределяет глобальную политику (как минимум влияют на то).</span><span class="sxs-lookup"><span data-stu-id="384c3-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="384c3-109">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="384c3-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="384c3-110">Можно настроить политики для управления доступом федеративных пользователей, даже в том случае, если вы не включили федерации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="384c3-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="384c3-111">Тем не менее политики, с помощью которых действуют только в том случае, если у вас есть федерации для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="384c3-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="384c3-112">Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="384c3-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="384c3-113">Кроме того при указании политики пользователя для управления доступом федеративных пользователей, политика применяется только к пользователям, которые включены для Скайп для Business Server и настроен для использования политики.</span><span class="sxs-lookup"><span data-stu-id="384c3-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="384c3-114">Чтобы настроить политику для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="384c3-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="384c3-115">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="384c3-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="384c3-116">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="384c3-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="384c3-117">В левой панели навигации щелкните **Доступ для внешних пользователей**и нажмите кнопку **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="384c3-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="384c3-118">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="384c3-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="384c3-119">Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей, щелкните глобальную политику, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="384c3-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="384c3-120">Чтобы создать новую политику сайта, нажмите кнопку **Создать**и выберите **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="384c3-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="384c3-121">В **разделе Выбор сайта**выберите требуемый сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="384c3-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="384c3-122">Чтобы создать новую политику пользователя, нажмите кнопку **Создать**и выберите **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="384c3-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="384c3-123">В **Новую внешнюю политику доступа**создайте уникальное имя в поле **имя** , которое указывает, какой пользователь политики освещает вопросы (например, **EnableFederatedUsers** для политики пользователя, которая разрешается связь для пользователей федеративного домена).</span><span class="sxs-lookup"><span data-stu-id="384c3-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="384c3-124">Чтобы изменить существующую политику, щелкните соответствующую политику, перечисленных в таблице, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="384c3-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="384c3-125">(Необязательно) Если вы хотите добавить или изменить описание, укажите информацию о политике в **поле Описание**.</span><span class="sxs-lookup"><span data-stu-id="384c3-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="384c3-126">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="384c3-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="384c3-127">Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="384c3-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="384c3-128">Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="384c3-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="384c3-129">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="384c3-129">Click **Commit**.</span></span>

<span data-ttu-id="384c3-130">Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федерации в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="384c3-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="384c3-131">Дополнительные сведения см [Включить или отключить федерацию и общедоступные службы обмена Мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="384c3-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="384c3-132">Если это политику уровня пользователя, также необходимо применить политику для пользователей, которые необходимо иметь возможность совместной работы с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="384c3-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="384c3-133">Дополнительные сведения см в [назначении политики доступа внешних пользователей](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="384c3-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="384c3-134">Чтобы настроить существующую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="384c3-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="384c3-135">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="384c3-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="384c3-136">Запустите Скайп для консоли Server бизнес: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="384c3-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="384c3-137">Введите следующие команды в Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="384c3-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="384c3-138">Параметр «EnablePublicCloudAudioVideoAccess» не имеет соответствующего выбора в Скайп панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="384c3-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="384c3-139">Чтобы создать новую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="384c3-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="384c3-140">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="384c3-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="384c3-141">Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="384c3-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="384c3-142">Введите следующие команды в Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="384c3-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="384c3-143">Пример создания новой политики сайта:</span><span class="sxs-lookup"><span data-stu-id="384c3-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="384c3-144">Чтобы удалить или сбросить политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="384c3-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="384c3-145">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="384c3-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="384c3-146">Введите следующую команду в Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="384c3-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="384c3-147">Пример Сброс глобальной политики (глобальной политики может иметь только его параметру удаленным.</span><span class="sxs-lookup"><span data-stu-id="384c3-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="384c3-148">Политика не может быть удалена):</span><span class="sxs-lookup"><span data-stu-id="384c3-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="384c3-149">Чтобы удалить политику сайта, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="384c3-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="384c3-150">Удаление политики сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="384c3-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="384c3-151">Чтобы удалить политику уровня пользователя с именем UserEAPPolicy, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="384c3-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="384c3-152">См. также</span><span class="sxs-lookup"><span data-stu-id="384c3-152">See Also</span></span>


[<span data-ttu-id="384c3-153">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="384c3-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="384c3-154">Назначьте политику доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="384c3-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="384c3-155">Управление федеративными доменами SIP для организации</span><span class="sxs-lookup"><span data-stu-id="384c3-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="384c3-156">Управление федеративными поставщиками SIP в организации</span><span class="sxs-lookup"><span data-stu-id="384c3-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="384c3-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="384c3-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="384c3-158">Новый CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="384c3-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="384c3-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="384c3-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="384c3-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="384c3-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="384c3-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="384c3-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

