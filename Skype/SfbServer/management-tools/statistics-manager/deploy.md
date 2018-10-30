---
title: Развертывание диспетчера статистики в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Сводка: Сведения о сведения о развертывании диспетчера статистики для Скайп для Business Server 2015.'
ms.openlocfilehash: 28ee68cc8770660587cb7d22d2ddd68c754a4fca
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838580"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="6871b-103">Deploy Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6871b-103">Deploy Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6871b-104">**Сводка:** В данном разделе приведены описан процесс развертывания диспетчера статистики для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6871b-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="6871b-105">Диспетчер статистики для Скайп для Business Server представляет собой мощное средство, которое позволяет просматривать Скайп для данные о работоспособности и производительности Business Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="6871b-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="6871b-106">Опрос данные о производительности на серверах сотни раз в несколько секунд и просмотреть результаты мгновенно на веб-сайт диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="6871b-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="6871b-107">Прежде чем пытаться установить диспетчер статистики, убедитесь, что вы знакомы с требования к программному обеспечению, сети и оборудования.</span><span class="sxs-lookup"><span data-stu-id="6871b-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="6871b-108">Для получения дополнительных сведений см. [Планирование для диспетчера статистики для Скайп для Business Server 2015](plan.md).</span><span class="sxs-lookup"><span data-stu-id="6871b-108">For more information, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6871b-109">При обновлении с предыдущей версии диспетчера статистики см.: [Обновление статистики диспетчер для Скайп для Business Server 2015](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="6871b-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server 2015](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6871b-110">Веб-сайт диспетчера статистики тестировался и корректно работает с браузерами Internet Explorer 11 и более поздних версий, Edge 20.10240 и более поздних версий и Chrome 46 и более поздних версий (текущая актуальная версия).</span><span class="sxs-lookup"><span data-stu-id="6871b-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="6871b-111">Можно найти диспетчер статистики загружаемые в [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="6871b-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="6871b-112">В этой статье содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="6871b-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="6871b-113">Развертывание диспетчера статистики</span><span class="sxs-lookup"><span data-stu-id="6871b-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="6871b-114">Поиск и устранение неполадок в развертывании</span><span class="sxs-lookup"><span data-stu-id="6871b-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="6871b-115">Создание самозаверяющего сертификата</span><span class="sxs-lookup"><span data-stu-id="6871b-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="6871b-116">Развертывание диспетчера статистики</span><span class="sxs-lookup"><span data-stu-id="6871b-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="6871b-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="6871b-117"></span></span>

<span data-ttu-id="6871b-118">Чтобы развернуть статистики Manager, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6871b-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="6871b-119">Подготовьте хост-компьютер прослушивателя, установив систему кэширования в памяти Redis и убедившись, что установлены все необходимые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="6871b-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="6871b-120">Установите службу прослушивателя на хост-компьютере. </span><span class="sxs-lookup"><span data-stu-id="6871b-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="6871b-121">Установите веб-сайт на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="6871b-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="6871b-122">Установите агент на каждом Скайп машины Business Server, которые вы хотите отслеживать.</span><span class="sxs-lookup"><span data-stu-id="6871b-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="6871b-123">Импортируйте топологию для отслеживаемых серверов.</span><span class="sxs-lookup"><span data-stu-id="6871b-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6871b-124">Система Redis, служба прослушивателя и веб-сайт должны быть установлены на одном хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="6871b-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="6871b-125">Убедитесь, что этот компьютер не Скайп Business Server установлена.</span><span class="sxs-lookup"><span data-stu-id="6871b-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="6871b-126">Подготовка хост-компьютера прослушивателя</span><span class="sxs-lookup"><span data-stu-id="6871b-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="6871b-127">Подготовка компьютера узла, необходимо будет установить системы кэширования в памяти Redis и убедитесь, что действующего сертификата на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6871b-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="6871b-128">Корпорация Майкрософт рекомендует установить последние стабильным построения Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="6871b-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="6871b-129">Статистика диспетчера версии 1.1 была протестирована Redis 3.0.501 и Redis 2.8.2400.</span><span class="sxs-lookup"><span data-stu-id="6871b-129">Statistics Manager version 1.1 was tested with Redis 3.0.501 and Redis 2.8.2400.</span></span> 
  
1. <span data-ttu-id="6871b-130">Загрузить Redis со следующего сайта: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="6871b-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="6871b-131">Можно загрузить неподписанный программы установки[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="6871b-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="6871b-132">При необходимости подписанные двоичные файлы можно получить через популярные диспетчеры пакетов — [Nuget](https://www.nuget.org/packages/Redis-64/) и [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="6871b-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="6871b-133">Запустите MSI-файл и следуйте указаниям.</span><span class="sxs-lookup"><span data-stu-id="6871b-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="6871b-134">Не устанавливайте флажок, добавляющий правило брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="6871b-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="6871b-135">Службе прослушивателя требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="6871b-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="6871b-136">Корпорация Майкрософт рекомендует, что у вас есть сертификат, подписанный с доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="6871b-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="6871b-137">Если вы хотите использовать самозаверяющий сертификат (например, для тестирования в лаборатории), см. раздел [Создание самозаверяющего сертификата](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="6871b-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="6871b-p106">Обратите внимание, что агент использует проверку по отпечатку сертификата (вместо проверки цепочки сертификатов). Он не будет выполнять полную проверку сертификатов, так как возможно использование самозаверяющих сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6871b-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="6871b-140">Установка службы прослушивателя</span><span class="sxs-lookup"><span data-stu-id="6871b-140">Install the Listener service</span></span>

<span data-ttu-id="6871b-141">Установите службы прослушивания на главном компьютере, запустив StatsManPerfAgentListener.msi и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="6871b-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="6871b-142">Изучите лицензионное соглашение. Если вы согласны, выберите пункт **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**. </span><span class="sxs-lookup"><span data-stu-id="6871b-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="6871b-143">На следующей странице введите указанную ниже информацию.</span><span class="sxs-lookup"><span data-stu-id="6871b-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="6871b-144">**Пароль службы**. Этот пароль будет использоваться удаленными агентами для проверки подлинности в службе прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="6871b-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="6871b-145">**Порта службы:** Это номер порта HTTPS, прослушиватель будет использоваться для связи с агентами.</span><span class="sxs-lookup"><span data-stu-id="6871b-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="6871b-146">Во время установки этот порт будет разрешен в локальном брандмауэре, будет создан список ACL для URL-адреса и к этому порту будет привязан SSL-сертификат.</span><span class="sxs-lookup"><span data-stu-id="6871b-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="6871b-147">Значение по умолчанию — 8443.</span><span class="sxs-lookup"><span data-stu-id="6871b-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="6871b-148">**Отпечаток сертификата:** Это отпечаток сертификата, который прослушиватель будет использоваться для шифрования протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6871b-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="6871b-149">Сетевая служба должна иметь доступ на чтение к закрытому ключу.</span><span class="sxs-lookup"><span data-stu-id="6871b-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="6871b-150">Для выбора отпечатка сертификата нажмите кнопку **Выбор...**.</span><span class="sxs-lookup"><span data-stu-id="6871b-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="6871b-151">Отпечаток сертификата можно найти с помощью диспетчера сертификатов или с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6871b-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="6871b-152">**Папка установки:** Это каталог, на котором будет установлен двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="6871b-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="6871b-153">Каталог по умолчанию можно изменить на другой с помощью кнопки **Обзор...**.</span><span class="sxs-lookup"><span data-stu-id="6871b-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="6871b-154">**AppData Dir:** Это каталог, в которой будут храниться папке Logs и другие данные.</span><span class="sxs-lookup"><span data-stu-id="6871b-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="6871b-155">Каталог по умолчанию можно изменить на другой.</span><span class="sxs-lookup"><span data-stu-id="6871b-155">You may change it from the default.</span></span> <span data-ttu-id="6871b-156">Он не будет удален при удалении программы.</span><span class="sxs-lookup"><span data-stu-id="6871b-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="6871b-157">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6871b-157">Click **Install**.</span></span>
    
<span data-ttu-id="6871b-158">Чтобы проверить установку, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="6871b-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="6871b-159">Откройте браузер и перейдите кhttps://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="6871b-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="6871b-160">По умолчанию порт службы — 8443 (если вы не задали другой порт).</span><span class="sxs-lookup"><span data-stu-id="6871b-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="6871b-161">Чтобы убедиться, что прослушиватель установлен правильно, проверьте следующие вещи.</span><span class="sxs-lookup"><span data-stu-id="6871b-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="6871b-162">Если страница проверки работоспособности отображается, прослушиватель установлен успешно.</span><span class="sxs-lookup"><span data-stu-id="6871b-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="6871b-163">Если значение KnownServersCount не меньше 1, то подключение к системе Redis установлено.</span><span class="sxs-lookup"><span data-stu-id="6871b-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="6871b-164">Подождав несколько минут и дождавшись установки по меньшей мере одного агента, посмотрите, увеличивается ли значение счетчика ValuesWritten.</span><span class="sxs-lookup"><span data-stu-id="6871b-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="6871b-165">Установка веб-сайта</span><span class="sxs-lookup"><span data-stu-id="6871b-165">Install the Website</span></span>

<span data-ttu-id="6871b-166">Установите веб-сайт, на главном компьютере, запустив StatsManWebSite.msi и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="6871b-166">Install the Website on the host machine by running the StatsManWebSite.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="6871b-167">Изучите лицензионное соглашение. Если вы согласны, выберите пункт **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**. </span><span class="sxs-lookup"><span data-stu-id="6871b-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="6871b-168">На следующей странице введите указанную ниже информацию.</span><span class="sxs-lookup"><span data-stu-id="6871b-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="6871b-169">**Порта службы:** Это номер порта, который выполняется прослушивание для веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="6871b-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="6871b-170">Его можно изменить позже, используя привязку порта в диспетчере служб IIS.</span><span class="sxs-lookup"><span data-stu-id="6871b-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="6871b-171">Во время установки этот порт будет разрешен в локальном брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="6871b-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="6871b-172">**Папка установки:** Это каталог, где будут установлены двоичные файлы.</span><span class="sxs-lookup"><span data-stu-id="6871b-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="6871b-173">Каталог по умолчанию можно изменить на другой с помощью кнопки **Обзор...**.</span><span class="sxs-lookup"><span data-stu-id="6871b-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="6871b-174">**AppData Dir:** Это каталог, в которой будут храниться папке Logs и другие данные.</span><span class="sxs-lookup"><span data-stu-id="6871b-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="6871b-175">Каталог по умолчанию можно изменить на другой.</span><span class="sxs-lookup"><span data-stu-id="6871b-175">You may change it from the default.</span></span> <span data-ttu-id="6871b-176">Он не будет удален при удалении программы.</span><span class="sxs-lookup"><span data-stu-id="6871b-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="6871b-177">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6871b-177">Click **Install**.</span></span>
    
<span data-ttu-id="6871b-178">Чтобы просмотреть веб-сайта, откройте браузер и перейдите к: http://localhost, webport\>/.</span><span class="sxs-lookup"><span data-stu-id="6871b-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="6871b-179">Чтобы просмотреть сведения только о работоспособности, откройте браузер и перейдите к: http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="6871b-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="6871b-180">По умолчанию номер веб-порта — 8080.</span><span class="sxs-lookup"><span data-stu-id="6871b-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="6871b-181">Привязку порта веб-сайта можно изменить с помощью диспетчера служб IIS.</span><span class="sxs-lookup"><span data-stu-id="6871b-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="6871b-182">Веб-установщик добавляет локальную группу безопасности с именем StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="6871b-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="6871b-183">В эту группу безопасности можно добавить учетные записи, которым нужно дать доступ к веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="6871b-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="6871b-184">Установка агентов</span><span class="sxs-lookup"><span data-stu-id="6871b-184">Install the Agents</span></span>

<span data-ttu-id="6871b-185">Установите агент на каждом Скайп для Business Server, который вы хотите отслеживать, запустив StatsManPerfAgent.msi и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="6871b-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="6871b-186">Изучите лицензионное соглашение. Если вы согласны, выберите пункт **Я принимаю условия лицензионного соглашения** и нажмите кнопку **Далее**. </span><span class="sxs-lookup"><span data-stu-id="6871b-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="6871b-187">На следующей странице введите указанную ниже информацию.</span><span class="sxs-lookup"><span data-stu-id="6871b-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="6871b-188">**Пароль службы**. Этот пароль будет использоваться удаленными агентами для проверки подлинности в службе прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="6871b-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="6871b-189">**Службы URI:** Это URI, где находится прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="6871b-190">Следует использовать https://name:port формат.</span><span class="sxs-lookup"><span data-stu-id="6871b-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="6871b-191">Можно использовать NetBIOS-имя или полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="6871b-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="6871b-192">Можно использовать имя, которое также указан как **Тема** или **Альтернативные имена субъекта** сертификата на службу прослушивателя, но это не является обязательным требованием.</span><span class="sxs-lookup"><span data-stu-id="6871b-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="6871b-193">**Службы отпечаток:** Это отпечаток SSL-сертификата, используемого прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="6871b-194">Этот отпечаток будет использоваться агентом для проверки подлинности в службе прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="6871b-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="6871b-195">(Он не будет выполнять полную проверку сертификатов, так как возможно использование самозаверяющих сертификатов.)</span><span class="sxs-lookup"><span data-stu-id="6871b-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="6871b-196">**Папка установки:** Это каталог, на котором будет установлен двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="6871b-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="6871b-197">Каталог по умолчанию можно изменить на другой с помощью кнопки **Обзор...**.</span><span class="sxs-lookup"><span data-stu-id="6871b-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="6871b-198">**AppData Dir:** Это каталог, в папке Logs и файл зашифрованные password.txt будет храниться.</span><span class="sxs-lookup"><span data-stu-id="6871b-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="6871b-199">Каталог по умолчанию можно изменить на другой.</span><span class="sxs-lookup"><span data-stu-id="6871b-199">You may thanks change it from the default.</span></span> <span data-ttu-id="6871b-200">Он не будет удален при удалении программы.</span><span class="sxs-lookup"><span data-stu-id="6871b-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="6871b-201">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="6871b-201">Click **Install**.</span></span>
    
<span data-ttu-id="6871b-p121">Если вы устанавливаете агент на несколько компьютеров, возможно, стоит сделать это в автоматическом режиме. Пример:  </span><span class="sxs-lookup"><span data-stu-id="6871b-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="6871b-204">импорт топологии</span><span class="sxs-lookup"><span data-stu-id="6871b-204">Import the topology</span></span>
<span data-ttu-id="6871b-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="6871b-205"></span></span>

<span data-ttu-id="6871b-206">После установки диспетчера статистики и запущен, необходимо импортировать Скайп для топологии Business Server таким образом, Менеджер Статистика знает сайта, пула и роли каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="6871b-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="6871b-207">Чтобы импортировать вашей Скайп для топологии Business Server, командлет [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) используется для получения сведений о каждом пуле, используемых в вашей организации, затем импортировать эти сведения в диспетчер статистики.</span><span class="sxs-lookup"><span data-stu-id="6871b-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="6871b-208">Чтобы импортировать Скайп для топологии Business Server, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6871b-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="6871b-209">На узле, который содержит Скайп по командлетам Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6871b-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="6871b-210">а.</span><span class="sxs-lookup"><span data-stu-id="6871b-210">a.</span></span> <span data-ttu-id="6871b-211">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="6871b-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="6871b-212">б.</span><span class="sxs-lookup"><span data-stu-id="6871b-212">b.</span></span> <span data-ttu-id="6871b-213">Скопируйте файл «mypoolinfo.xml» на сервер, на котором выполняется прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="6871b-214">На хосте, на котором запущен прослушиватель:</span><span class="sxs-lookup"><span data-stu-id="6871b-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="6871b-215">а.</span><span class="sxs-lookup"><span data-stu-id="6871b-215">a.</span></span> <span data-ttu-id="6871b-216">Запустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6871b-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="6871b-217">б.</span><span class="sxs-lookup"><span data-stu-id="6871b-217">b.</span></span> <span data-ttu-id="6871b-218">Перейдите в каталог, куда установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="6871b-219">По умолчанию это:</span><span class="sxs-lookup"><span data-stu-id="6871b-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="6871b-220">Чтобы проверить, какие серверы добавляются и обновляются, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6871b-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="6871b-221">Следующая команда позволяет увидеть все параметры:</span><span class="sxs-lookup"><span data-stu-id="6871b-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="6871b-222">Для просмотра сведений в настоящее время импортированных сервера, выполните следующий скрипт:</span><span class="sxs-lookup"><span data-stu-id="6871b-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="6871b-223">Если вы хотите отслеживать серверах, не входящих в вашей Скайп для топологии Business Server — сервер Exchange Server, например можно сделать импорта одного сервера на главном компьютере, на котором выполняется прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="6871b-224">Чтобы выполнить импорт для одного сервера, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="6871b-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="6871b-225">Перейдите в каталог, куда установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="6871b-226">По умолчанию это:</span><span class="sxs-lookup"><span data-stu-id="6871b-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="6871b-227">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="6871b-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="6871b-228">Поиск и устранение неполадок в развертывании</span><span class="sxs-lookup"><span data-stu-id="6871b-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="6871b-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="6871b-229"></span></span>

<span data-ttu-id="6871b-230">Если агент не запускается, проверьте следующее. </span><span class="sxs-lookup"><span data-stu-id="6871b-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="6871b-231">Агент, зарегистрированный в диспетчере статистики?</span><span class="sxs-lookup"><span data-stu-id="6871b-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="6871b-p129">	Убедитесь, что вы выполнили инструкции по импорту топологии. См. статью [Импорт топологии](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="6871b-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="6871b-234">Если агент находится на сервере, который не указан в топологии (например, узлы в кластере SQL AlwaysOn), необходимо добавить агент вручную, следуя инструкциям в статье [Импорт топологии](deploy.md#BKMK_ImportTopology).</span><span class="sxs-lookup"><span data-stu-id="6871b-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="6871b-235">Может ли агент установить контакт с прослушивателем?</span><span class="sxs-lookup"><span data-stu-id="6871b-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="6871b-236">Убедитесь, что служба прослушивателя запущена.  </span><span class="sxs-lookup"><span data-stu-id="6871b-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="6871b-237">Если служба не запущена, убедитесь, что система Redis запущена, а затем попробуйте перезапустить прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="6871b-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="6871b-238">Убедитесь, что порт открыт в службу прослушивателя, и, что компьютер агента обмениваться данными с номер порта.</span><span class="sxs-lookup"><span data-stu-id="6871b-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="6871b-239">Чтобы убедиться, что статистика диспетчер сбор данных, можно проверить CSV-файла следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6871b-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="6871b-240">Следующая команда получает имена хранилищ счетчика:  </span><span class="sxs-lookup"><span data-stu-id="6871b-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="6871b-241">Следующая команда получает значения указанных счетчиков: </span><span class="sxs-lookup"><span data-stu-id="6871b-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="6871b-242">Сведения о всех событий, которые могут отображаться в журнале событий приложений см.: [Устранение неполадок диспетчер статистики для Скайп для Business Server 2015](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="6871b-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server 2015](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="6871b-243">Создание самозаверяющего сертификата</span><span class="sxs-lookup"><span data-stu-id="6871b-243">Create a self-signed certificate</span></span>
<span data-ttu-id="6871b-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="6871b-244"></span></span>

<span data-ttu-id="6871b-245">Майкрософт настоятельно рекомендует использовать сертификат, подписанный надежным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="6871b-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="6871b-246">Если же вы хотите использовать самозаверяющий сертификат в целях тестирования, сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="6871b-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="6871b-247">Выполнив вход от имени администратора, введите в консоли PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6871b-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="6871b-248">Тип `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="6871b-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="6871b-249">Откроется диспетчер сертификатов для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="6871b-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="6871b-250">Перейдите на **Личные**, а затем откройте **сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="6871b-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="6871b-251">Щелкните правой кнопкой мыши на **StatsManListener -\>все задачи -\>управление закрытых ключей...**</span><span class="sxs-lookup"><span data-stu-id="6871b-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="6871b-252">Нажмите кнопку \*\*Добавить \*\*.</span><span class="sxs-lookup"><span data-stu-id="6871b-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="6871b-253">В поле **Введите имена выбираемых объектов** введите "Сетевая служба"</span><span class="sxs-lookup"><span data-stu-id="6871b-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="6871b-254">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6871b-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="6871b-p132">В разделе **Полный доступ** снимите флажок **Разрешить**. (Необходим только доступ на чтение.)</span><span class="sxs-lookup"><span data-stu-id="6871b-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="6871b-257">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6871b-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="6871b-258">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6871b-258">For more information</span></span>
<span data-ttu-id="6871b-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="6871b-259"></span></span>

<span data-ttu-id="6871b-260">Дополнительные сведения приведены далее.</span><span class="sxs-lookup"><span data-stu-id="6871b-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="6871b-261">Plan for Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6871b-261">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="6871b-262">Upgrade Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6871b-262">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>](upgrade.md)
    
- [<span data-ttu-id="6871b-263">Troubleshoot Statistics Manager for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6871b-263">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="6871b-264">Блог, посвященный диспетчеру статистики Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6871b-264">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

