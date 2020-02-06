---
title: Настройка политик управления доступом федеративных пользователей
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов. '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818320"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="62858-103">Настройка политик для управления доступом федеративных пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="62858-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="62858-104">Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="62858-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="62858-105">Вы можете настроить одну или несколько политик доступа внешних пользователей, чтобы указать, могут ли пользователи федеративных доменов работать совместно с пользователями сервера Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="62858-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="62858-106">Чтобы управлять федеративным доступом пользователей, вы можете настроить политики на уровне Global, site и User.</span><span class="sxs-lookup"><span data-stu-id="62858-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="62858-107">Параметры политики Skype для бизнеса Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="62858-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="62858-108">Приоритет политики в Skype для бизнеса Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="62858-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="62858-109">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="62858-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="62858-110">Вы можете настроить политики для управления доступом к федеративным пользователям, даже если вы не включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="62858-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="62858-111">Тем не менее, настроенные политики действуют только в том случае, если включена Федерация для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="62858-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="62858-112">Дополнительные сведения о включении Федерации можно найти в разделе [Включение и отключение удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="62858-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="62858-113">Кроме того, если указать политику пользователей для управления доступом федеративного пользователя, политика применяется только для пользователей, которые включены в Skype для бизнеса Server и настроены на использование политики.</span><span class="sxs-lookup"><span data-stu-id="62858-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="62858-114">Настройка политики для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="62858-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="62858-115">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="62858-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62858-116">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="62858-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="62858-117">На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="62858-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="62858-118">На странице " **политика внешней доступа** " выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="62858-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="62858-119">Чтобы настроить глобальную политику для поддержки федеративного доступа пользователей, выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="62858-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="62858-120">Чтобы создать новую политику сайта, нажмите кнопку **создать**и выберите пункт **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="62858-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="62858-121">В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="62858-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="62858-122">Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="62858-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="62858-123">В **новой политике внешнего доступа**Создайте уникальное имя в поле Name ( **имя** ), которое указывает политику пользователя (например, **енаблефедератедусерс** для политики пользователя, которая включает связь для пользователей федеративного домена).</span><span class="sxs-lookup"><span data-stu-id="62858-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="62858-124">Чтобы изменить существующую политику, выберите соответствующую политику, указанную в таблице, и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="62858-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="62858-125">Необязательно Если вы хотите добавить или изменить описание, укажите сведения о политике в **описании**.</span><span class="sxs-lookup"><span data-stu-id="62858-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="62858-126">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="62858-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="62858-127">Чтобы включить для политики федеративного доступа пользователей, установите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="62858-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="62858-128">Чтобы отключить федеративного доступа пользователей для политики, снимите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="62858-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="62858-129">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="62858-129">Click **Commit**.</span></span>

<span data-ttu-id="62858-130">Для включения федеративного доступа пользователей необходимо также включить поддержку Федерации в Организации.</span><span class="sxs-lookup"><span data-stu-id="62858-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="62858-131">Дополнительные сведения можно найти в разделе [Включение и отключение подключения к службам федерации и общедоступных мгновенных сообщений](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="62858-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="62858-132">Если это политика пользователя, необходимо также применить политику для пользователей, которые должны быть доступны для совместной работы с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="62858-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="62858-133">Подробности можно найти в разделе [назначение внешней политики доступа пользователей](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="62858-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="62858-134">Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="62858-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="62858-135">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="62858-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62858-136">Запустите консоль управления сервером Skype для визитной: нажмите кнопку **Пуск**, выберите **все программы**, а затем — Skype для бизнеса **Server**, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="62858-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="62858-137">В командной консоли Skype для бизнеса Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="62858-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="62858-138">Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выделения на панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="62858-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="62858-139">Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="62858-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="62858-140">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="62858-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62858-141">Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Skype**для бизнеса Server, а затем — **Командная консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="62858-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="62858-142">В командной консоли Skype для бизнеса Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="62858-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="62858-143">Ниже приведен пример создания новой политики сайта.</span><span class="sxs-lookup"><span data-stu-id="62858-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="62858-144">Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="62858-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="62858-145">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="62858-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="62858-146">В командной консоли Skype для бизнеса Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="62858-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="62858-147">Пример сброса глобальной политики (Глобальная политика может быть удалена только из нее.</span><span class="sxs-lookup"><span data-stu-id="62858-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="62858-148">Не удается удалить политику.</span><span class="sxs-lookup"><span data-stu-id="62858-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="62858-149">Чтобы удалить политику сайта, введите:</span><span class="sxs-lookup"><span data-stu-id="62858-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="62858-150">Удаление политики сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="62858-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="62858-151">Чтобы удалить политику пользователя с именем Усереапполици, введите:</span><span class="sxs-lookup"><span data-stu-id="62858-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="62858-152">См. также</span><span class="sxs-lookup"><span data-stu-id="62858-152">See Also</span></span>


[<span data-ttu-id="62858-153">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="62858-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="62858-154">Назначение политики доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="62858-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="62858-155">Управление федеративными доменами SIP для организации</span><span class="sxs-lookup"><span data-stu-id="62858-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="62858-156">Управление федеративными поставщиками SIP в организации</span><span class="sxs-lookup"><span data-stu-id="62858-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="62858-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="62858-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="62858-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="62858-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="62858-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="62858-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="62858-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="62858-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="62858-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="62858-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

