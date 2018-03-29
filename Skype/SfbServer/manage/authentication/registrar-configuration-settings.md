---
title: Управление параметрами конфигурации регистратора в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Сводка: Управление параметров конфигурации регистратора для Скайп для Business Server 2015.'
ms.openlocfilehash: 5cdcf1cba045f5105b1f375fbcebb22b7b00a25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="afdd8-103">Управление параметрами конфигурации регистратора в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="afdd8-103">Manage Registrar configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="afdd8-104">**Сводка:** Управление параметрами конфигурации регистратора для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afdd8-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="afdd8-p101">Регистратор можно использовать для настройки способов проверки подлинности прокси-сервера. Заданный протокол проверки подлинности определяет, какой тип запросов серверы в пуле выдают клиентам. Далее приводятся доступные протоколы.</span><span class="sxs-lookup"><span data-stu-id="afdd8-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="afdd8-108">**Kerberos** Это надежную схему проверки подлинности на основе пароля, доступных для клиентов, но обычно доступны только для корпоративных клиентов, так как требуется подключение к клиенту для центр распространения ключей (контроллер домена Kerberos).</span><span class="sxs-lookup"><span data-stu-id="afdd8-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="afdd8-109">Это значение можно выбрать в том случае, если на сервере проверяется подлинность только корпоративных клиентов.</span><span class="sxs-lookup"><span data-stu-id="afdd8-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="afdd8-110">**NTLM** Это пароль проверки подлинности на основе недоступны для клиентов, использующих хеширование запрос ответ на пароль.</span><span class="sxs-lookup"><span data-stu-id="afdd8-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="afdd8-111">Это единственная форма проверки подлинности, доступная клиентам без подключения к центру распространения ключей (контроллеру домена Kerberos), в том числе удаленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="afdd8-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="afdd8-112">Если на сервере проверяется подлинность только удаленных пользователей, следует выбрать значение NTLM.</span><span class="sxs-lookup"><span data-stu-id="afdd8-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="afdd8-113">**Проверка подлинности сертификата** Это новый метод проверки подлинности сервера необходимо получить сертификаты из клиентов Lync Phone Edition, телефонов общего пользования, Скайп для бизнеса и приложение Lync магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="afdd8-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="afdd8-114">На клиентах Lync Phone Edition, после того как пользователь входит в и успешно проходит проверку подлинности с указанием персонального идентификационного номера (ПИН-кода), Скайп для Business Server 2015, затем подготавливает URI SIP на номер телефона, и подпись подготавливает Скайп для Business Server сертификат или сертификат пользователя, который определяет Джо (например: SN=joe@contoso.com) на номер телефона.</span><span class="sxs-lookup"><span data-stu-id="afdd8-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server 2015 then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="afdd8-115">Этот сертификат применяется при проверке подлинности с помощью регистратора и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="afdd8-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="afdd8-p105">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="afdd8-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="afdd8-120">При использовании клиентов приложение Lync магазина Windows, необходимо включить проверку подлинности сертификата.</span><span class="sxs-lookup"><span data-stu-id="afdd8-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="afdd8-121">Создание параметров конфигурации нового регистратора</span><span class="sxs-lookup"><span data-stu-id="afdd8-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="afdd8-122">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afdd8-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="afdd8-123">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="afdd8-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="afdd8-124">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="afdd8-125">На странице **Регистратор** щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="afdd8-126">В поле **Выбор службы** выберите службу, к которой требуется применить регистратор, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="afdd8-127">На странице **Создание новой настройки регистратора** установите один или несколько флажков в зависимости от возможностей клиентов.</span><span class="sxs-lookup"><span data-stu-id="afdd8-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="afdd8-128">**Включить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="afdd8-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="afdd8-129">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="afdd8-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="afdd8-130">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="afdd8-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="afdd8-131">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="afdd8-132">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="afdd8-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="afdd8-133">Регистратор можно использовать для настройки прокси-сервера протоколы проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="afdd8-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="afdd8-134">Сведения о доступных протоколов см. [в Скайп для Business Server 2015 параметры конфигурации управление регистратора](registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="afdd8-134">For information about the available protocols, see [Manage Registrar configuration settings in Skype for Business Server 2015](registrar-configuration-settings.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afdd8-p107">Если сервер поддерживает проверку подлинности для удаленных клиентов и для клиентов предприятия, рекомендуется включить и Kerberos, и NTLM. Пограничный сервер и внутренние серверы взаимодействуют, чтобы убедиться, что для удаленных клиентов предлагается только проверка подлинности NTLM. Если на этих серверах включен только Kerberos, они не могут выполнять проверку подлинности удаленных пользователей. Если пользователи предприятия также проходят проверку подлинности на сервере, то используется Kerberos.</span><span class="sxs-lookup"><span data-stu-id="afdd8-p107">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="afdd8-139">Чтобы изменить параметры службы Регистратора, выполните действия, описанные в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="afdd8-139">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="afdd8-140">Изменение параметров конфигурации существующего регистратора</span><span class="sxs-lookup"><span data-stu-id="afdd8-140">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="afdd8-141">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afdd8-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="afdd8-142">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="afdd8-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="afdd8-143">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-143">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="afdd8-144">На странице **Регистратор** щелкните службу, затем щелкните **Изменить** (Изменить) и **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-144">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="afdd8-145">На странице **редактирования параметров регистратора** установите один или несколько флажков в зависимости от возможностей клиентов и наличия поддержки в среде.</span><span class="sxs-lookup"><span data-stu-id="afdd8-145">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="afdd8-146">**Разрешить проверку подлинности Kerberos**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="afdd8-146">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="afdd8-147">**Разрешить проверку подлинности NTLM**. В этом режиме серверы в пуле выдают запросы с применением проверки подлинности NTLM.</span><span class="sxs-lookup"><span data-stu-id="afdd8-147">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="afdd8-148">**Разрешить проверку подлинности на основе сертификатов**. В этом режиме серверы в пуле выдают сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="afdd8-148">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="afdd8-149">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-149">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="afdd8-150">Удаление параметров конфигурации регистратора</span><span class="sxs-lookup"><span data-stu-id="afdd8-150">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="afdd8-151">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="afdd8-151">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="afdd8-152">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="afdd8-152">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="afdd8-153">В левой области навигации щелкните **Безопасность**, затем **Регистратор**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-153">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="afdd8-154">На странице **Регистратор** полностью или частично введите в поле поиска имя регистратора, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="afdd8-154">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="afdd8-155">Выберите в списке требуемый регистратор, затем щелкните **Изменить** и **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-155">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="afdd8-156">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="afdd8-156">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="afdd8-157">Удаление параметров конфигурации регистратора с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="afdd8-157">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="afdd8-158">С помощью Windows PowerShell и командлет **Remove-CsProxyConfiguration** можно удалить параметров конфигурации регистратора.</span><span class="sxs-lookup"><span data-stu-id="afdd8-158">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="afdd8-159">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afdd8-159">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="afdd8-160">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="afdd8-160">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="afdd8-161">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="afdd8-161">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="afdd8-162">Удаление определенного набора параметров безопасности Регистратора</span><span class="sxs-lookup"><span data-stu-id="afdd8-162">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="afdd8-163">Следующая команда удаляет параметры безопасности Регистратора, применяемые к пограничному серверу atl-edge-011.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="afdd8-163">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="afdd8-164">Удаление всех параметров безопасности Регистратора, применяемых на уровне сайта</span><span class="sxs-lookup"><span data-stu-id="afdd8-164">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="afdd8-165">Следующая команда удаляет все параметры безопасности Регистратора, применяемые к службе Регистратора.</span><span class="sxs-lookup"><span data-stu-id="afdd8-165">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="afdd8-166">Удаление всех параметров безопасности Регистратора, разрешающих проверку подлинности NTLM</span><span class="sxs-lookup"><span data-stu-id="afdd8-166">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="afdd8-167">Следующая команда удаляет все параметры безопасности Регистратора, разрешающие использование NTLM для проверки подлинности клиентов.</span><span class="sxs-lookup"><span data-stu-id="afdd8-167">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="afdd8-168">Дополнительные сведения см [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="afdd8-168">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

