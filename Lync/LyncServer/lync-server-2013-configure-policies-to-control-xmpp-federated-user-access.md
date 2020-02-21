---
title: 'Lync Server 2013: Настройка политик для управления доступом федеративного пользователя XMPP'
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
ms.openlocfilehash: 31889fa60f86d269e5efab696c2c27e48cc55d59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="0b1d1-102">Настройка политик для управления доступом федеративных пользователей XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1d1-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b1d1-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0b1d1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0b1d1-104">Это Предварительная документация, которая может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="0b1d1-105">Пустые разделы включены в качестве заполнителей.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="0b1d1-106">При настройке политик для поддержки федеративных партнеров XMPP (расширяемый протокол обмена сообщениями и контроля присутствия) политики применяют к пользователям федеративных доменов XMPP, а не к пользователям поставщиков (например, Windows Live) услуг обмена мгновенными сообщениями по протоколу SIP (Session Initiation Protocol) или федеративных доменов SIP.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="0b1d1-107">**Федеративного партнера XMPP** настраивают для каждого федеративного домена XMPP, в котором пользователям разрешается добавлять контакты и взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="0b1d1-108">Политики федеративных партнеров XMPP доступны только в одной области, хотя политика не определяется как глобальная, она действует как глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="0b1d1-109">Чтобы определить для федеративных партнеров XMPP глобальную политику, политику уровня сайта или пользователя, настраивают область действия политики путем создания и настройки политики внешнего доступа для требуемой области действия.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="0b1d1-110">Сведения о типах политик, которые можно настроить для внешнего доступа и Федерации, приведены в статье [Управление федерациями и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b1d1-111">Все политики <STRONG>федерации и внешнего доступа</STRONG> применяются через предоставление внутренних полос.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="0b1d1-112">Политики, которые применяются к пользователям, принадлежат сайту или являются глобальными по области действия, доводятся до клиента во время входа в систему.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="0b1d1-113">Политики для управления доступом федеративных партнеров XMPP можно настроить, даже если для вашей организации не включена XMPP-федерация.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="0b1d1-114">Однако настраиваемые политики вступают в действие, только когда для организации развернута, включена и настроена федерация партнеров XMPP.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="0b1d1-115">Подробные сведения о развертывании и настройке Федерации XMPP Partner приведены в статье <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="0b1d1-116">Кроме того, если вы укажете политику пользователя в политике внешнего доступа для управления федеративными партнерами XMPP, политика применяется только к пользователям, поддерживающим Lync Server 2013 и настроенным на использование политики.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="0b1d1-117">Чтобы изменить глобальную политику для федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="0b1d1-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="0b1d1-118">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1d1-119">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b1d1-120">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0b1d1-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b1d1-121">На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="0b1d1-122">На странице **Политика внешнего доступа** выполните следующие действия в отношении глобальной политики:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="0b1d1-123">Выберите глобальную политику, щелкните **Изменить**, а затем щелкните "Подробнее".</span><span class="sxs-lookup"><span data-stu-id="0b1d1-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="0b1d1-124">Предоставьте описание глобальной политики (по желанию).</span><span class="sxs-lookup"><span data-stu-id="0b1d1-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="0b1d1-125">Выберите настройку **Разрешить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="0b1d1-126">Выберите **Enable communications with XMPP federated users** (Разрешить взаимодействие с федеративными пользователями XMPP).</span><span class="sxs-lookup"><span data-stu-id="0b1d1-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="0b1d1-127">Щелкните **Зафиксировать**, чтобы сохранить изменения в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="0b1d1-128">Чтобы создать политику уровня сайта или пользователя для федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="0b1d1-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="0b1d1-p105">Щелкните **Создать**, а затем щелкните **Политика уровня сайта** или **Политика уровня пользователя**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="0b1d1-131">Предоставьте описание политики сайта (по желанию).</span><span class="sxs-lookup"><span data-stu-id="0b1d1-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="0b1d1-132">В политике уровня сайта или пользователя выберите настройку **Разрешить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="0b1d1-133">Выберите пункт **Разрешить связь с федеративными пользователями XMPP**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="0b1d1-134">Щелкните **Зафиксировать**, чтобы сохранить изменения в политике сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="0b1d1-135">Чтобы изменить существующую политику для федеративных партнеров XMPP</span><span class="sxs-lookup"><span data-stu-id="0b1d1-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="0b1d1-136">Чтобы изменить существующую политику, выберите соответствующую политику в списке, щелкните **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="0b1d1-137">Измените или обновите описание политики (по желанию).</span><span class="sxs-lookup"><span data-stu-id="0b1d1-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="0b1d1-138">Выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="0b1d1-139">выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями XMPP**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="0b1d1-140">Щелкните **Зафиксировать**, чтобы сохранить изменения в политике.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="0b1d1-141">Изменение существующей политики для федеративных партнеров XMPP с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1d1-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="0b1d1-142">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1d1-143">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0b1d1-144">Введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="0b1d1-145">Пример команды, которая задаст глобальную политику для доступа федеративных пользователей в true (Enabled) и доступ домена XMPP к true (включено):</span><span class="sxs-lookup"><span data-stu-id="0b1d1-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="0b1d1-146">Создание политики сайта или пользователя для федеративных партнеров XMPP с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1d1-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="0b1d1-147">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1d1-148">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0b1d1-149">Введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="0b1d1-150">Пример команды, устанавливающей политику уровня сайта для сайта Редмонда с целью разрешить доступ федеративных пользователей и разрешить доступ в XMPP-домен:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="0b1d1-151">Удаление существующей политики для федеративных партнеров XMPP с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b1d1-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="0b1d1-152">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0b1d1-153">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0b1d1-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0b1d1-154">Введите в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="0b1d1-155">Пример команды, удаляющей политику уровня пользователя:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="0b1d1-156">Пример команды, сбрасывающей глобальную политику в настройки по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="0b1d1-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b1d1-157">См. также</span><span class="sxs-lookup"><span data-stu-id="0b1d1-157">See Also</span></span>


[<span data-ttu-id="0b1d1-158">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1d1-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="0b1d1-159">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1d1-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="0b1d1-160">Управление федеративными партнерами XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b1d1-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="0b1d1-161">Set — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0b1d1-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="0b1d1-162">New — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0b1d1-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="0b1d1-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0b1d1-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="0b1d1-164">Remove — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0b1d1-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="0b1d1-165">Granting — CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="0b1d1-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

