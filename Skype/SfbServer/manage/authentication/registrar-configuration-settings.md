---
title: Управление параметрами конфигурации регистратора в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Сводка: Управление параметрами настройки регистратора в Skype для бизнеса Server.'
ms.openlocfilehash: 8aac78f782b7a9db23d3bb124943c55cdbd8565a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992306"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7ae7f-103">Управление параметрами конфигурации регистратора в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7ae7f-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7ae7f-104">**Сводка:** Управление параметрами конфигурации регистраторов для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="7ae7f-p101">Регистратор можно использовать для настройки способов проверки подлинности прокси-сервера. Заданный протокол проверки подлинности определяет, какой тип запросов серверы в пуле выдают клиентам. Далее приводятся доступные протоколы.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="7ae7f-108">**Kerberos** Это надежная схема проверки подлинности на основе паролей, доступная для клиентов, но она обычно доступна только для корпоративных клиентов, так как для этого требуется подключение клиента к центру распространения ключей (контроллер домена Kerberos).</span><span class="sxs-lookup"><span data-stu-id="7ae7f-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="7ae7f-109">Это значение можно выбрать в том случае, если на сервере проверяется подлинность только корпоративных клиентов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="7ae7f-110">**NTLM** Это проверка подлинности на основе пароля, доступная для клиентов, использующих в пароле схему хеширования с запросом ответа.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="7ae7f-111">Это единственная форма проверки подлинности, доступная клиентам без подключения к центру распространения ключей (контроллеру домена Kerberos), в том числе удаленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="7ae7f-112">Если на сервере проверяется подлинность только удаленных пользователей, следует выбрать значение NTLM.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="7ae7f-113">**Проверка подлинности сертификата** Это новый способ проверки подлинности, когда сервер должен получить сертификаты от клиентов Lync Phone Edition, обычных телефонов, Skype для бизнеса и приложения Lync из Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="7ae7f-114">На клиентах Lync Phone Edition после входа пользователя в систему и успешной проверки подлинности, предоставляя персональный идентификационный номер (ПИН-код), приложение Skype для бизнеса Server затем подготавливает универсальный код ресурса (URI) к телефону и подготавливает сертификат пользователя, подписанный сервером Skype для бизнеса, или сертификат, который определяет Сергей (например, SN=joe@contoso.com) на телефон.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="7ae7f-115">Этот сертификат применяется при проверке подлинности с помощью регистратора и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ae7f-p105">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="7ae7f-120">Если вы используете приложения Lync из Магазина Windows, необходимо включить проверку подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="7ae7f-121">Создание параметров конфигурации нового регистратора</span><span class="sxs-lookup"><span data-stu-id="7ae7f-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="7ae7f-122">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="7ae7f-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="7ae7f-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7ae7f-124">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="7ae7f-125">На странице **Регистратор** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="7ae7f-126">В поле **Выбор службы** выберите службу, к которой требуется применить регистратор, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="7ae7f-127">На странице **Создание новой настройки регистратора** установите один или несколько флажков в зависимости от возможностей клиентов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="7ae7f-128">**Включить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="7ae7f-129">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="7ae7f-130">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="7ae7f-131">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="7ae7f-132">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="7ae7f-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="7ae7f-133">Вы можете использовать регистратор для настройки протоколов проверки подлинности прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7ae7f-p106">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="7ae7f-138">Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="7ae7f-139">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="7ae7f-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="7ae7f-140">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="7ae7f-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="7ae7f-141">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7ae7f-142">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="7ae7f-143">На странице **Регистратор** щелкните службу, затем щелкните **Изменить** (Изменить) и **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="7ae7f-144">На странице **редактирования параметров регистратора** установите один или несколько флажков в зависимости от возможностей клиентов и наличия поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="7ae7f-145">**Разрешить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="7ae7f-146">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="7ae7f-147">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="7ae7f-148">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="7ae7f-149">Удаление параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="7ae7f-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="7ae7f-150">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="7ae7f-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="7ae7f-151">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7ae7f-152">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="7ae7f-153">На странице **Регистратор** полностью или частично введите в поле поиска имя регистратора, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="7ae7f-154">Выберите в списке требуемый регистратор, затем щелкните **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="7ae7f-155">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ae7f-156">Удаление параметров конфигурации регистратора с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ae7f-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7ae7f-157">Вы можете удалить параметры конфигурации регистратора с помощью Windows PowerShell и командлета **Remove-кспроксиконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="7ae7f-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="7ae7f-158">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7ae7f-159">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7ae7f-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7ae7f-160">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="7ae7f-161">Удаление определенного набора параметров безопасности Регистратора</span><span class="sxs-lookup"><span data-stu-id="7ae7f-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="7ae7f-162">Следующая команда удаляет параметры безопасности Регистратора, применяемые к пограничному серверу atl-edge-011.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="7ae7f-163">Удаление всех параметров безопасности Регистратора, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="7ae7f-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="7ae7f-164">Следующая команда удаляет все параметры безопасности Регистратора, применяемые к службе Регистратора.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="7ae7f-165">Удаление всех параметров безопасности Регистратора, разрешающих проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="7ae7f-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="7ae7f-166">Следующая команда удаляет все параметры безопасности Регистратора, разрешающие использование NTLM для проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="7ae7f-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="7ae7f-167">Подробности можно найти в разделе [Remove-кспроксиконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7ae7f-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

