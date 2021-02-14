---
title: Управление настройками веб-служб в Skype для бизнеса Server
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: Сводка. Управление настройками конфигурации веб-служб в Skype для бизнеса Server.
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806499"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="58426-103">Управление настройками веб-служб в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="58426-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="58426-104">**Сводка:** Управление настройками веб-служб в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="58426-105">Страницу **веб-службы** можно использовать для настройки методов проверки подлинности для доступа к веб-серверам и веб-службам, связанным со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="58426-106">Чтобы создать политику веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="58426-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="58426-107">Создание новых параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="58426-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="58426-108">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="58426-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="58426-110">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="58426-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="58426-111">На странице **Веб-служба** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="58426-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="58426-p101">Чтобы настроить веб-службу для сайта, щелкните **Конфигурация сайта**. В разделе **выбора сайта** щелкните сайт, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="58426-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="58426-p102">Чтобы настроить веб-службу для пула, щелкните **Конфигурация пула**. В разделе **выбора службы** щелкните службу, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="58426-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="58426-116">На странице **Создание параметров веб-службы** в раскрывающемся списке **Встроенная проверка подлинности Windows** выберите **Согласование**, **Встроенная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="58426-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="58426-117">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="58426-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="58426-118">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="58426-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="58426-119">**Включить проверку подлинности с использованием сертификатов**, чтобы разрешить серверам пула выдавать сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="58426-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="58426-120">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="58426-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="58426-121">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="58426-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="58426-122">Изменение существующих параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="58426-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="58426-123">Страницу **веб-службы** можно использовать для настройки методов проверки подлинности для доступа к веб-серверам и веб-службам, связанным со Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="58426-124">Чтобы изменить политику существующей веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="58426-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="58426-125">Изменение существующих параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="58426-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="58426-126">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="58426-127">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="58426-128">В левой панели навигации щелкните **Безопасность** и затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="58426-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="58426-129">На странице **Веб-служба**  выберите конфигурацию, щелкните **Изменить** и затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="58426-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="58426-130">На странице **Изменение параметров веб-службы** в раскрывающемся списке **Интегрированная проверка подлинности Windows** выберите **Согласование**, **Интегрированная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="58426-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="58426-131">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="58426-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="58426-132">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="58426-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="58426-133">**Включить проверку подлинности с использованием сертификатов**, чтобы разрешить серверам пула выдавать сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="58426-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="58426-134">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="58426-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="58426-135">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="58426-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="58426-136">Удаление существующих параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="58426-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="58426-137">Выполните следующие действия, чтобы удалить параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="58426-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="58426-138">Удаление параметров конфигурации веб-службы</span><span class="sxs-lookup"><span data-stu-id="58426-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="58426-139">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="58426-140">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="58426-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="58426-141">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="58426-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="58426-142">На странице **Веб-служба** в поле поиска введите полностью или частично имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="58426-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="58426-143">В списке политик выберите необходимую политику, щелкните **Правка** и затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="58426-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="58426-144">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="58426-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="58426-145">Удаление параметров конфигурации веб-службы с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="58426-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="58426-146">Параметры конфигурации веб-службы можно удалить с помощью Windows PowerShell и с помощью Windows PowerShell **Remove-CsWebServiceConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="58426-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="58426-147">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58426-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="58426-148">Подробные сведения об использовании удаленного Windows PowerShell для подключения к Skype для бизнеса Server см. в статье [блога "Краткое руководство. Управление Microsoft Lync Server 2010 с помощью удаленной службы PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="58426-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="58426-149">В Skype для бизнеса Server этот процесс тот же.</span><span class="sxs-lookup"><span data-stu-id="58426-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="58426-150">Удаление конкретной коллекции параметров конфигурации веб-служб</span><span class="sxs-lookup"><span data-stu-id="58426-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="58426-151">Следующая команда удаляет параметры безопасности веб-служб, относящиеся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="58426-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="58426-152">Удаление всех параметров конфигурации веб-служб, применяемых к области сайта</span><span class="sxs-lookup"><span data-stu-id="58426-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="58426-153">Следующая команда удаляет все параметры безопасности веб-служб, относящиеся к области службы:</span><span class="sxs-lookup"><span data-stu-id="58426-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="58426-154">Удаление всех параметров конфигурации веб-службы, которые позволяют проверить подлинность сертификата</span><span class="sxs-lookup"><span data-stu-id="58426-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="58426-155">Следующая команда удаляет все параметры безопасности веб-служб, позволяющие использовать проверку подлинности с помощью сертификатов:</span><span class="sxs-lookup"><span data-stu-id="58426-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="58426-156">Подробные сведения см. в [подстройки Remove-CsWebServiceConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="58426-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

