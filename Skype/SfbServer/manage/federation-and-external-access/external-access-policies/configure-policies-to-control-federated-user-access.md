---
title: Настройка политик для управления доступом федеративных пользователей
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: 'При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817309"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="67ed9-103">Настройка политик для управления доступом федераированных пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="67ed9-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="67ed9-104">При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="67ed9-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="67ed9-105">Вы можете настроить одну или несколько политик доступа внешних пользователей, чтобы контролировать возможность совместной работы пользователей федераированных доменов с пользователями Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="67ed9-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="67ed9-106">Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="67ed9-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="67ed9-107">Параметры политики Skype для бизнеса Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="67ed9-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="67ed9-108">Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние). </span><span class="sxs-lookup"><span data-stu-id="67ed9-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="67ed9-109">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="67ed9-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="67ed9-110">Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации.</span><span class="sxs-lookup"><span data-stu-id="67ed9-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="67ed9-111">Однако настроенные политики вступают в силу только при включении федерации для организации.</span><span class="sxs-lookup"><span data-stu-id="67ed9-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="67ed9-112">Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](../access-edge/enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="67ed9-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="67ed9-113">Кроме того, если вы указываете политику пользователей для управления доступом федераированных пользователей, эта политика применяется только к пользователям, которые включены в Skype для бизнеса Server и настроены на использование этой политики.</span><span class="sxs-lookup"><span data-stu-id="67ed9-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="67ed9-114">Чтобы настроить политику для поддержку доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="67ed9-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="67ed9-115">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="67ed9-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ed9-116">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="67ed9-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="67ed9-117">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="67ed9-118">На странице **Политика внешнего доступа** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="67ed9-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="67ed9-119">Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей? щелкните глобальную политику, щелкните **Изменить**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="67ed9-p103">Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="67ed9-p104">Чтобы создать новую политику пользователей, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Новая политика внешнего доступа** создайте уникальное имя в поле **Имя**, которое указывает, что охватывается политикой пользователей (например, **EnableFederatedUsers** для политики пользователей, которая разрешает связь с пользователями федеративных доменов).</span><span class="sxs-lookup"><span data-stu-id="67ed9-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="67ed9-124">Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="67ed9-125">(Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="67ed9-126">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="67ed9-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="67ed9-127">Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="67ed9-128">Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="67ed9-129">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="67ed9-129">Click **Commit**.</span></span>

<span data-ttu-id="67ed9-130">Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации.</span><span class="sxs-lookup"><span data-stu-id="67ed9-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="67ed9-131">Подробные сведения см. в [подключите или отключите федерацию и подключение к общедоступным системам im.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="67ed9-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="67ed9-132">Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="67ed9-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="67ed9-133">Дополнительные сведения см. в [дополнительных сведениях о назначении политики доступа внешних пользователей.](assign-an-external-user-access-policy.md)</span><span class="sxs-lookup"><span data-stu-id="67ed9-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="67ed9-134">Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федератных доменов</span><span class="sxs-lookup"><span data-stu-id="67ed9-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="67ed9-135">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="67ed9-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ed9-136">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **Server",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="67ed9-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="67ed9-137">Введите следующую запись в оболочке управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="67ed9-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="67ed9-138">Параметр "EnablePublicCloudAudioVideoAccess" не имеет соответствующего выбора в панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="67ed9-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="67ed9-139">Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федераированных доменов</span><span class="sxs-lookup"><span data-stu-id="67ed9-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="67ed9-140">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="67ed9-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ed9-141">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Microsoft Skype для бизнеса **Server",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="67ed9-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="67ed9-142">Введите следующую запись в оболочке управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="67ed9-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="67ed9-143">Пример создания новой политики сайта:</span><span class="sxs-lookup"><span data-stu-id="67ed9-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="67ed9-144">Удаление или сброс политики с Windows PowerShell для поддержки доступа пользователей федератных доменов</span><span class="sxs-lookup"><span data-stu-id="67ed9-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="67ed9-145">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="67ed9-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="67ed9-146">Введите следующую запись в оболочке управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="67ed9-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="67ed9-p107">Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):</span><span class="sxs-lookup"><span data-stu-id="67ed9-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="67ed9-149">Чтобы удалить политику сайта, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="67ed9-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="67ed9-150">Удаляет политику сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="67ed9-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="67ed9-151">Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="67ed9-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="67ed9-152">См. также</span><span class="sxs-lookup"><span data-stu-id="67ed9-152">See Also</span></span>


[<span data-ttu-id="67ed9-153">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="67ed9-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="67ed9-154">Назначение политики доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="67ed9-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="67ed9-155">Управление федеративными доменами SIP для организации</span><span class="sxs-lookup"><span data-stu-id="67ed9-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="67ed9-156">Управление федеративными поставщиками SIP в организации</span><span class="sxs-lookup"><span data-stu-id="67ed9-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="67ed9-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67ed9-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="67ed9-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67ed9-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="67ed9-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67ed9-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="67ed9-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67ed9-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="67ed9-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="67ed9-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

