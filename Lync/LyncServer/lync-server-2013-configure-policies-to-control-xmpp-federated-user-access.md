---
title: 'Lync Server 2013: настройка политик управления доступом федеративных XMPP-пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="950e4-102">Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="950e4-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="950e4-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="950e4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="950e4-104">Это предварительная редакция документации и она может меняться.</span><span class="sxs-lookup"><span data-stu-id="950e4-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="950e4-105">Пустые разделы добавлены в качестве заполнителей.</span><span class="sxs-lookup"><span data-stu-id="950e4-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="950e4-106">Если вы настраиваете политики для поддержки федеративных партнеров по протоколу расширенного обмена сообщениями (КСМПП), политики применяются к пользователям КСМПП федеративных доменов, но не к пользователям служб мгновенных сообщений в протоколе запуска сеансов (SIP). (например, Windows Live) или федеративные домены SIP.</span><span class="sxs-lookup"><span data-stu-id="950e4-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="950e4-107">Вы настраиваете **федеративного партнера КСМПП** для каждого КСМПП федеративного домена, с которым вы хотите разрешить пользователям добавлять контакты и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="950e4-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="950e4-108">Политики федеративного партнера КСМПП доступны только в одной области, хотя она не определена как Глобальная, действует как Глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="950e4-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="950e4-109">Чтобы определить политику глобального, сайта или пользователя для партнеров Федерации КСМПП, настройте область политики, сначала создав и настроив политику внешнего доступа для нужной области.</span><span class="sxs-lookup"><span data-stu-id="950e4-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="950e4-110">Подробные сведения о типах политик, которые можно настроить для внешнего доступа и интеграции, приведены в разделе [Управление интеграцией и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="950e4-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="950e4-111">Все политики <STRONG>Федерации и внешнего доступа</STRONG> применяются при подготовке по каналу.</span><span class="sxs-lookup"><span data-stu-id="950e4-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="950e4-112">Политики, которые применяются к пользователю, принадлежат сайту или являются глобальными в области, передаются клиенту во время входа.</span><span class="sxs-lookup"><span data-stu-id="950e4-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="950e4-113">Вы можете настроить политики для управления доступом КСМПП федеративного партнера, даже если вы не включили КСМПП Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="950e4-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="950e4-114">Тем не менее настроенные политики вступают в силу только в том случае, если у вас развернута, включена и настроена федерация КСМППных партнеров для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="950e4-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="950e4-115">Подробные сведения о развертывании и настройке Федерации КСМПП Partner можно найти <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">в разделе Настройка Федерации SIP, Федерации КСМПП и общедоступной службы обмена мгновенными сообщениями в приложении Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="950e4-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="950e4-116">Кроме того, если вы укажете политику пользователя во внешней политике доступа для управления КСМПП федеративными партнерами, политика применяется только к пользователям, которые включены в Lync Server 2013 и настроены на использование политики.</span><span class="sxs-lookup"><span data-stu-id="950e4-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="950e4-117">Изменение глобальной политики для федеративных партнеров КСМПП</span><span class="sxs-lookup"><span data-stu-id="950e4-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="950e4-118">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="950e4-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="950e4-119">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="950e4-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="950e4-120">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="950e4-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="950e4-121">На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.</span><span class="sxs-lookup"><span data-stu-id="950e4-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="950e4-122">На странице " **политика внешней доступа** " выполните указанные ниже действия для глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="950e4-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="950e4-123">Выберите глобальную политику, нажмите кнопку **изменить**и выберите пункт Показать подробности.</span><span class="sxs-lookup"><span data-stu-id="950e4-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="950e4-124">Введите описание глобальной политики (необязательно).</span><span class="sxs-lookup"><span data-stu-id="950e4-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="950e4-125">Выберите **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="950e4-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="950e4-126">Выберите **включить связь с федеративными пользователями КСМПП**.</span><span class="sxs-lookup"><span data-stu-id="950e4-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="950e4-127">Нажмите **кнопку Сохранить,** чтобы сохранить изменения в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="950e4-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="950e4-128">Создание политики сайта или пользователя для федеративных партнеров КСМПП</span><span class="sxs-lookup"><span data-stu-id="950e4-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="950e4-129">Нажмите кнопку **создать**, а затем выберите пункт **Политика сайта** или **Политика пользователя**.</span><span class="sxs-lookup"><span data-stu-id="950e4-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="950e4-130">В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="950e4-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="950e4-131">Введите описание политики сайта (необязательно).</span><span class="sxs-lookup"><span data-stu-id="950e4-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="950e4-132">В разделе Политика сайта или пользователя выберите **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="950e4-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="950e4-133">Выберите **включить связь с федеративными пользователями КСМПП**.</span><span class="sxs-lookup"><span data-stu-id="950e4-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="950e4-134">Нажмите **кнопку Сохранить,** чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="950e4-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="950e4-135">Изменение существующей политики для федеративных партнеров КСМПП</span><span class="sxs-lookup"><span data-stu-id="950e4-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="950e4-136">Чтобы изменить существующую политику, выберите соответствующую политику в списке, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="950e4-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="950e4-137">Измените или обновите описание политики (необязательно).</span><span class="sxs-lookup"><span data-stu-id="950e4-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="950e4-138">Установите или снимите флажок **включить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="950e4-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="950e4-139">Установите или снимите флажок **включить связь с федеративными пользователями КСМПП**.</span><span class="sxs-lookup"><span data-stu-id="950e4-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="950e4-140">Нажмите **кнопку Сохранить,** чтобы сохранить изменения в политике.</span><span class="sxs-lookup"><span data-stu-id="950e4-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="950e4-141">Изменение существующей политики для федеративных партнеров КСМПП с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="950e4-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="950e4-142">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="950e4-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="950e4-143">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="950e4-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="950e4-144">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="950e4-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="950e4-145">Пример команды, с помощью которой можно настроить глобальную политику для доступа федеративного пользователя к true (Enabled) и доступ домена КСМПП к значению true (включено):</span><span class="sxs-lookup"><span data-stu-id="950e4-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="950e4-146">Создание политики сайта или пользователя для федеративных партнеров КСМПП с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="950e4-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="950e4-147">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="950e4-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="950e4-148">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="950e4-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="950e4-149">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="950e4-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="950e4-150">Пример команды, которая позволяет настроить политику сайта для сайта Redmond для федеративного доступа пользователей к разрешенным и КСМПП доменам.</span><span class="sxs-lookup"><span data-stu-id="950e4-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="950e4-151">Удаление существующей политики для федеративных партнеров КСМПП с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="950e4-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="950e4-152">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="950e4-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="950e4-153">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="950e4-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="950e4-154">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="950e4-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="950e4-155">Пример команды, которая удалит политику пользователя:</span><span class="sxs-lookup"><span data-stu-id="950e4-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="950e4-156">Пример команды, которая будет сбрасывать для глобальной политики значения по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="950e4-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="950e4-157">См. также</span><span class="sxs-lookup"><span data-stu-id="950e4-157">See Also</span></span>


[<span data-ttu-id="950e4-158">Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="950e4-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="950e4-159">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="950e4-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="950e4-160">Управление федеративными XMPP-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="950e4-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="950e4-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="950e4-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="950e4-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="950e4-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="950e4-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="950e4-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="950e4-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="950e4-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="950e4-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="950e4-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

