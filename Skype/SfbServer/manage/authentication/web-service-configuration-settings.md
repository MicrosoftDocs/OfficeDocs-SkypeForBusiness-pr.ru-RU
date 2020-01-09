---
title: Управление параметрами конфигурации веб-службы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Сводка: Управление параметрами конфигурации веб-службы в Skype для бизнеса Server.'
ms.openlocfilehash: 383b85e156dfdbc6af7606da49d4cf89bf655698
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991934"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a768e-103">Управление параметрами конфигурации веб-службы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a768e-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a768e-104">**Сводка:** Управление параметрами конфигурации веб-службы в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a768e-105">Страницу **веб-службы** можно использовать для настройки способов проверки подлинности для доступа к веб-серверам и веб-службам, связанным с Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="a768e-106">Чтобы создать политику веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a768e-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="a768e-107">Создание параметров конфигурации новой веб-службы</span><span class="sxs-lookup"><span data-stu-id="a768e-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="a768e-108">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="a768e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a768e-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a768e-110">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="a768e-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="a768e-111">На странице **Веб-служба** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a768e-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="a768e-p101">Чтобы настроить веб-службу для сайта, щелкните **Конфигурация сайта**. В разделе **выбора сайта** щелкните сайт, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a768e-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="a768e-p102">Чтобы настроить веб-службу для пула, щелкните **Конфигурация пула**. В разделе **выбора службы** щелкните службу, к которому должна применяться эта политика веб-службы, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a768e-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="a768e-116">На странице **Создание параметров веб-службы** в раскрывающемся списке **Встроенная проверка подлинности Windows** выберите **Согласование**, **Встроенная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="a768e-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="a768e-117">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="a768e-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a768e-118">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="a768e-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="a768e-119">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="a768e-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="a768e-120">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="a768e-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="a768e-121">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a768e-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="a768e-122">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="a768e-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="a768e-123">Страницу **веб-службы** можно использовать для настройки способов проверки подлинности для доступа к веб-серверам и веб-службам, связанным с Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="a768e-124">Чтобы изменить политику существующей веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a768e-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="a768e-125">Изменение параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="a768e-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="a768e-126">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="a768e-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a768e-127">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a768e-128">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="a768e-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="a768e-129">На странице **Веб-служба** выберите конфигурацию, щелкните **Правка**, затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="a768e-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a768e-130">На странице **Изменение параметров веб-службы** в раскрывающемся списке **Интегрированная проверка подлинности Windows** выберите **Согласование**, **Интегрированная проверка подлинности Windows** или **Отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="a768e-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="a768e-131">Установите один флажок или несколько флажков в соответствии с возможностями клиентов и среды:</span><span class="sxs-lookup"><span data-stu-id="a768e-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="a768e-132">**Включить проверку подлинности с помощью ПИН-кода**, чтобы разрешить клиентам проходить проверку подлинности с помощью ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="a768e-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="a768e-133">**Включить проверку подлинности с помощью сертификата** — чтобы серверы в пуле выдавали сертификаты клиентам.</span><span class="sxs-lookup"><span data-stu-id="a768e-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="a768e-134">**Включить загрузку цепочки сертификатов**, чтобы серверы, представляющие сертификат проверки подлинности, загружали цепочку сертификатов для этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="a768e-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="a768e-135">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a768e-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="a768e-136">Удаление параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="a768e-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="a768e-137">Чтобы удалить параметры конфигурации веб-службы, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a768e-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="a768e-138">Удаление параметров конфигурации существующей веб-службы</span><span class="sxs-lookup"><span data-stu-id="a768e-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="a768e-139">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="a768e-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a768e-140">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a768e-141">В левой панели навигации щелкните **Безопасность**, а затем щелкните **Веб-служба**.</span><span class="sxs-lookup"><span data-stu-id="a768e-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="a768e-142">На странице **Веб-служба** в поле поиска введите полностью или частично имя политики, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="a768e-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="a768e-143">В списке политик выберите необходимую политику, щелкните **Правка**, затем выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="a768e-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="a768e-144">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a768e-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a768e-145">Удаление параметров конфигурации веб-службы с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a768e-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a768e-146">Вы можете удалить параметры конфигурации веб-службы с помощью Windows PowerShell и командлета **Remove-ксвебсервицеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="a768e-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="a768e-147">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a768e-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a768e-148">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="a768e-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a768e-149">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a768e-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="a768e-150">Удаление конкретной коллекции параметров конфигурации веб-служб</span><span class="sxs-lookup"><span data-stu-id="a768e-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="a768e-151">Следующая команда удаляет параметры безопасности веб-служб, относящиеся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="a768e-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="a768e-152">Удаление всех параметров конфигурации веб-служб, относящихся к области сайта</span><span class="sxs-lookup"><span data-stu-id="a768e-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="a768e-153">Следующая команда удаляет все параметры безопасности веб-служб, относящиеся к области службы:</span><span class="sxs-lookup"><span data-stu-id="a768e-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="a768e-154">Удаление всех параметров конфигурации веб-служб, позволяющих проверку подлинности с помощью сертификатов</span><span class="sxs-lookup"><span data-stu-id="a768e-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="a768e-155">Следующая команда удаляет все параметры безопасности веб-служб, позволяющие использовать проверку подлинности с помощью сертификатов:</span><span class="sxs-lookup"><span data-stu-id="a768e-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="a768e-156">Подробности можно найти в разделе [Remove-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a768e-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

