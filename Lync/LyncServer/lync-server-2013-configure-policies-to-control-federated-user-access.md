---
title: 'Lync Server 2013: настройка политик управления доступом федеративных пользователей'
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
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="8701f-102">Настройка политик управления доступом федеративных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8701f-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8701f-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="8701f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="8701f-104">Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="8701f-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="8701f-105">Вы можете настроить одну или несколько политик доступа внешних пользователей, чтобы указать, могут ли пользователи федеративных доменов работать совместно с пользователями Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8701f-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="8701f-106">Чтобы управлять федеративным доступом пользователей, вы можете настроить политики на уровне Global, site и User.</span><span class="sxs-lookup"><span data-stu-id="8701f-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="8701f-107">Параметры политики сервера Lync Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики.</span><span class="sxs-lookup"><span data-stu-id="8701f-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="8701f-108">Приоритет политики Lync Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние).</span><span class="sxs-lookup"><span data-stu-id="8701f-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="8701f-109">То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.</span><span class="sxs-lookup"><span data-stu-id="8701f-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8701f-110">Вы можете настроить политики для управления доступом к федеративным пользователям, даже если вы не включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="8701f-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="8701f-111">Тем не менее, настроенные политики действуют только в том случае, если включена Федерация для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8701f-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="8701f-112">Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="8701f-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="8701f-113">Кроме того, если вы укажете политику пользователей для управления доступом пользователей Федерации, политика применяется только для пользователей, которые включены в Lync Server 2013 и настроены на использование политики.</span><span class="sxs-lookup"><span data-stu-id="8701f-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="8701f-114">Настройка политики для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="8701f-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="8701f-115">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8701f-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8701f-116">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8701f-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8701f-117">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8701f-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8701f-118">На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="8701f-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="8701f-119">На странице " **политика внешней доступа** " выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="8701f-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="8701f-120">Чтобы настроить глобальную политику для поддержки федеративного доступа пользователей, выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="8701f-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="8701f-121">Чтобы создать новую политику сайта, нажмите кнопку **создать**и выберите пункт **Политика сайта**.</span><span class="sxs-lookup"><span data-stu-id="8701f-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="8701f-122">В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8701f-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="8701f-123">Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8701f-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="8701f-124">В **новой политике внешнего доступа**Создайте уникальное имя в поле Name ( **имя** ), которое указывает политику пользователя (например, **енаблефедератедусерс** для политики пользователя, которая включает связь для пользователей федеративного домена).</span><span class="sxs-lookup"><span data-stu-id="8701f-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="8701f-125">Чтобы изменить существующую политику, выберите соответствующую политику, указанную в таблице, и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="8701f-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8701f-126">Необязательно Если вы хотите добавить или изменить описание, укажите сведения о политике в **описании**.</span><span class="sxs-lookup"><span data-stu-id="8701f-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="8701f-127">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="8701f-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="8701f-128">Чтобы включить для политики федеративного доступа пользователей, установите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="8701f-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="8701f-129">Чтобы отключить федеративного доступа пользователей для политики, снимите флажок **включить связь с федеративными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="8701f-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="8701f-130">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="8701f-130">Click **Commit**.</span></span>

<span data-ttu-id="8701f-131">Для включения федеративного доступа пользователей необходимо также включить поддержку Федерации в Организации.</span><span class="sxs-lookup"><span data-stu-id="8701f-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="8701f-132">Дополнительные сведения можно найти [в разделе Включение и отключение службы подключения к службам федерации и общедоступных сообщений в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8701f-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="8701f-133">Если это политика пользователя, необходимо также применить политику для пользователей, которые должны быть доступны для совместной работы с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="8701f-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="8701f-134">Подробности можно найти в разделе [назначение внешней политики доступа пользователю Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="8701f-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="8701f-135">Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="8701f-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="8701f-136">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8701f-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8701f-137">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8701f-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8701f-138">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8701f-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="8701f-139">Пример команды, которая позволяет настроить глобальную политику для доступа федеративных пользователей на разрешенные, КСМПП доступ к домену для включения, доступа к общедоступным поставщикам для включения и предоставления возможности использования звуковых и видеофайлов для общедоступных поставщиков, поддерживающих этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8701f-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="8701f-140">Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выделения на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8701f-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="8701f-141">Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="8701f-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="8701f-142">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8701f-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8701f-143">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8701f-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8701f-144">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8701f-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="8701f-145">Ниже приведен пример создания новой политики сайта.</span><span class="sxs-lookup"><span data-stu-id="8701f-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="8701f-146">Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов</span><span class="sxs-lookup"><span data-stu-id="8701f-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="8701f-147">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8701f-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8701f-148">Введите следующую команду в командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8701f-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="8701f-149">Пример сброса глобальной политики (Глобальная политика может быть удалена только из нее.</span><span class="sxs-lookup"><span data-stu-id="8701f-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="8701f-150">Не удается удалить политику.</span><span class="sxs-lookup"><span data-stu-id="8701f-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="8701f-151">Чтобы удалить политику сайта, введите:</span><span class="sxs-lookup"><span data-stu-id="8701f-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="8701f-152">Удаление политики сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="8701f-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="8701f-153">Чтобы удалить политику пользователя с именем Усереапполици, введите:</span><span class="sxs-lookup"><span data-stu-id="8701f-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8701f-154">См. также</span><span class="sxs-lookup"><span data-stu-id="8701f-154">See Also</span></span>


[<span data-ttu-id="8701f-155">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8701f-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="8701f-156">Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8701f-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="8701f-157">Управление федеративными доменами SIP для организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8701f-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="8701f-158">Управление федеративными поставщиками SIP в организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8701f-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="8701f-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8701f-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="8701f-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8701f-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="8701f-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8701f-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="8701f-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8701f-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="8701f-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8701f-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

