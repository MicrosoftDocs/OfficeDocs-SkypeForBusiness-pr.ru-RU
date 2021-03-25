---
title: Управление настройками регистратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: Сводка. Управление настройками конфигурации регистратора для Skype для бизнеса Server.
ms.openlocfilehash: a1cd1048ea37a249126ec892560312a482459d44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119578"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="bcbbf-103">Управление настройками регистратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="bcbbf-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="bcbbf-104">**Сводка:** Управление настройками реестра для Skype для бизнес-сервера.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="bcbbf-p101">Регистратор можно использовать для настройки способов проверки подлинности прокси-сервера. Заданный протокол проверки подлинности определяет, какой тип запросов серверы в пуле выдают клиентам. Далее приводятся доступные протоколы.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="bcbbf-108">**Kerberos** Это самая сильная схема проверки подлинности на основе паролей, доступная клиентам, но обычно она доступна только корпоративным клиентам, так как для этого требуется подключение клиента к центру рассылки ключей (контроллер домена Kerberos).</span><span class="sxs-lookup"><span data-stu-id="bcbbf-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="bcbbf-109">Этот протокол подходит, если сервер проверяет подлинность только клиентов предприятия.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="bcbbf-110">**NTLM** Это проверка подлинности на основе паролей для клиентов, которые используют схему хаширования вызовов на пароль.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="bcbbf-111">Это единственная форма проверки подлинности, доступная клиентам без подключения к центру распространения ключей (контроллеру домена Kerberos), таким как удаленные пользователи.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="bcbbf-112">Если сервер проверяет подлинность только удаленных пользователей, то следует выбрать NTLM.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="bcbbf-113">**Проверка подлинности сертификатов** Это новый метод проверки подлинности, когда серверу необходимо получать сертификаты от клиентов Lync Phone Edition, телефонов общей области, Skype для бизнеса и приложения Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="bcbbf-114">На клиентах Lync Phone Edition после того, как пользователь войдет и успешно прошел проверку подлинности, предоставив личный идентификационный номер (PIN), Skype для бизнеса Server затем предоставляет SIP URI на телефон и предоставляет сертификат подписи Skype для бизнеса Server или сертификат пользователя, идентифицирующий Джо (Ex: SN=joe@contoso.com) на телефон.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="bcbbf-115">Этот сертификат используется для проверки подлинности с помощью регистратора и веб-служб</span><span class="sxs-lookup"><span data-stu-id="bcbbf-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bcbbf-p105">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="bcbbf-120">Если вы будете использовать клиентов приложений Lync Windows Store, необходимо включить проверку подлинности сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="bcbbf-121">Создание новых параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="bcbbf-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="bcbbf-122">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bcbbf-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bcbbf-124">В левой панели навигации последовательно выберите пункты **Безопасность** и **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bcbbf-125">На странице **регистратора** нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="bcbbf-126">В поле **выбора службы** выберите службу, к которой должен быть применен регистратор, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="bcbbf-127">В разделе **Настройка нового регистратора** установите какие-либо из следующих флажков, в зависимости от возможностей клиентов и поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="bcbbf-128">**Включить проверку подлинности Kerberos** — чтобы серверы в пуле выдавали запросы с использованием проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="bcbbf-129">**Включить проверку подлинности NTLM** — чтобы серверы в пуле выдавали запросы с использованием NTLM.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="bcbbf-130">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="bcbbf-131">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bcbbf-132">Изменение существующих параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="bcbbf-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="bcbbf-133">Для настройки протоколов проверки подлинности прокси-сервера можно использовать службу Регистратора.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bcbbf-p106">Если сервер обеспечивает проверку подлинности удаленных клиентов и клиентов организации, то рекомендуется включить проверку подлинности Kerberos и NTLM. Пограничный сервер и внутренние серверы проверяют, включена ли проверка подлинности NTLM для удаленных клиентов. Если на этих серверах включена только проверка подлинности Kerberos, они не смогут выполнять проверку подлинности удаленных пользователей. Если пользователи организации проходят проверку подлинности на сервере, то используется протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="bcbbf-138">Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="bcbbf-139">Изменение существующих параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="bcbbf-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="bcbbf-140">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bcbbf-141">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bcbbf-142">В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).</span><span class="sxs-lookup"><span data-stu-id="bcbbf-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bcbbf-143">На странице **Registrar** (Регистратор) выберите службу, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="bcbbf-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bcbbf-144">На странице **Edit Registrar Setting** (Изменение параметров Регистратора) установите один флажок или несколько в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="bcbbf-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="bcbbf-145">**Enable Kerberos authentication** (Включить проверку подлинности Kerberos) — для запросов проверки подлинности серверы пула используют протокол Kerberos.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="bcbbf-146">**Включить проверку подлинности NTLM** — чтобы серверы в пуле выдавали запросы с использованием NTLM.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="bcbbf-147">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="bcbbf-148">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="bcbbf-149">Удаление параметров конфигурации Регистратора</span><span class="sxs-lookup"><span data-stu-id="bcbbf-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="bcbbf-150">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bcbbf-151">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bcbbf-152">В левой панели навигации щелкните **Security** (Безопасность) и затем щелкните **Registrar** (Регистратор).</span><span class="sxs-lookup"><span data-stu-id="bcbbf-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="bcbbf-153">На странице **Registrar** (Регистратор) введите имя удаляемого Регистратора или часть имени в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="bcbbf-154">Выберите требуемого Регистратора, а затем щелкните **Edit** (Изменить) и **Delete** (Удалить).</span><span class="sxs-lookup"><span data-stu-id="bcbbf-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="bcbbf-155">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bcbbf-156">Удаление параметров конфигурации регистратора с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="bcbbf-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bcbbf-157">Параметры конфигурации регистратора можно удалить с помощью Windows PowerShell и **cmdlet Remove-CsProxyConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="bcbbf-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="bcbbf-158">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bcbbf-159">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="bcbbf-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="bcbbf-160">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="bcbbf-161">Удаление определенного набора параметров безопасности Регистратора</span><span class="sxs-lookup"><span data-stu-id="bcbbf-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="bcbbf-162">Следующая команда удаляет параметры безопасности Регистратора, применяемые к пограничному серверу atl-edge-011.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="bcbbf-163">Удаление всех параметров безопасности Регистратора, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="bcbbf-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="bcbbf-164">Следующая команда удаляет все параметры безопасности Регистратора, применяемые к службе Регистратора.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="bcbbf-165">Удаление всех параметров безопасности Регистратора, разрешающих проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="bcbbf-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="bcbbf-166">Следующая команда удаляет все параметры безопасности Регистратора, разрешающие использование NTLM для проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="bcbbf-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="bcbbf-167">Подробнее см. в [материале Remove-CsProxyConfiguration.](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bcbbf-167">For details, see [Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
