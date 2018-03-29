---
title: Управление параметрами конфигурации веб-службы в Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Сводка: Управление параметрами конфигурации веб-службы в Скайп для Business Server 2015.'
ms.openlocfilehash: a0976728ecd09392408fb719861681e0465d7bed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="5a2c0-103">Управление параметрами конфигурации веб-службы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="5a2c0-103">Manage Web Service configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5a2c0-104">**Сводка:** Управление параметрами конфигурации веб-службы в Скайп Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5a2c0-105">Страница **Веб-службы** можно использовать для настройки методов проверки подлинности для доступа к Скайп для Business Server 2015 связанных с веб-серверов и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="5a2c0-106">Чтобы создать политику веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-107">Создание параметров конфигурации новой веб-службы</span><span class="sxs-lookup"><span data-stu-id="5a2c0-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="5a2c0-108">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5a2c0-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5a2c0-110">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="5a2c0-111">На странице **Веб-служба** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="5a2c0-p101">Чтобы настроить веб-службу для сайта, щелкните **Конфигурация сайта**. В разделе **выбора сайта** щелкните сайт, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="5a2c0-p102">Чтобы настроить веб-службу для пула, щелкните **Конфигурация пула**. В разделе **выбора службы** щелкните службу, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="5a2c0-116">На странице **Создание параметров веб-службы** в раскрывающемся списке **Встроенная проверка подлинности Windows** выберите **Согласование**, **Встроенная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="5a2c0-117">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="5a2c0-118">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="5a2c0-119">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="5a2c0-120">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="5a2c0-121">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-122">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="5a2c0-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="5a2c0-123">Страница **Веб-службы** можно использовать для настройки методов проверки подлинности для доступа к Скайп для Business Server 2015 связанных с веб-серверов и веб-служб.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server 2015 related web servers and Web Services.</span></span>
  
<span data-ttu-id="5a2c0-124">Чтобы изменить политику существующей веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-125">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="5a2c0-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="5a2c0-126">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5a2c0-127">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5a2c0-128">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="5a2c0-129">На странице **Веб-служба** выберите конфигурацию, щелкните **Правка**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="5a2c0-130">На странице **Изменение параметров веб-службы** в раскрывающемся списке **Интегрированная проверка подлинности Windows** выберите **Согласование**, **Интегрированная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="5a2c0-131">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="5a2c0-132">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="5a2c0-133">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="5a2c0-134">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="5a2c0-135">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-136">Удаление параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="5a2c0-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="5a2c0-137">Чтобы удалить параметры конфигурации веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-138">Удаление параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="5a2c0-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="5a2c0-139">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="5a2c0-140">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5a2c0-141">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="5a2c0-142">На странице **Веб-служба** в поле поиска введите полностью или частично имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="5a2c0-143">В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5a2c0-144">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5a2c0-145">Удаление параметров конфигурации веб-службы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a2c0-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5a2c0-146">С помощью Windows PowerShell и командлет **Remove-CsWebServiceConfiguration** можно удалить параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="5a2c0-147">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5a2c0-148">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="5a2c0-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5a2c0-149">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a2c0-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="5a2c0-150">Удаление конкретной коллекции параметров конфигурации веб-служб</span><span class="sxs-lookup"><span data-stu-id="5a2c0-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="5a2c0-151">Следующая команда удаляет параметры безопасности веб-служб, относящиеся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="5a2c0-152">Удаление всех параметров конфигурации веб-служб, относящихся к области сайта</span><span class="sxs-lookup"><span data-stu-id="5a2c0-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="5a2c0-153">Следующая команда удаляет все параметры безопасности веб-служб, относящиеся к области службы:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="5a2c0-154">Удаление всех параметров конфигурации веб-служб, позволяющих проверку подлинности с помощью сертификатов</span><span class="sxs-lookup"><span data-stu-id="5a2c0-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="5a2c0-155">Следующая команда удаляет все параметры безопасности веб-служб, позволяющие использовать проверку подлинности с помощью сертификатов:</span><span class="sxs-lookup"><span data-stu-id="5a2c0-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="5a2c0-156">Дополнительные сведения см [Командлет Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a2c0-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

