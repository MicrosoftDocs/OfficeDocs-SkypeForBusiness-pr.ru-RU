---
title: Развертывание диспетчера статистики в Skype для бизнеса Server
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
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: Сводка. В этом разделе вы узнаете, как развернуть диспетчер статистики в Skype для бизнеса Server.
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814819"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="60e0d-103">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="60e0d-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="60e0d-104">**Сводка:** В этом разделе вы узнаете, как развернуть диспетчер статистики в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="60e0d-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="60e0d-105">Диспетчер статистики для Skype для бизнеса Server — это мощное средство, которое позволяет просматривать данные о работоспособности и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="60e0d-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="60e0d-106">Вы можете опросить данные о производительности на нескольких сотнях серверов каждые несколько секунд и мгновенно просмотреть результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="60e0d-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="60e0d-107">Перед установкой диспетчера статистики необходимо ознакомиться с требованиями к программному обеспечению, сети и оборудованию.</span><span class="sxs-lookup"><span data-stu-id="60e0d-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="60e0d-108">Дополнительные сведения см. в сведениях о планировании [диспетчера статистики для Skype для бизнеса Server.](plan.md)</span><span class="sxs-lookup"><span data-stu-id="60e0d-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="60e0d-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="60e0d-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="60e0d-110">Веб-сайт диспетчера статистики протестирован и правильно работает в Internet Explorer 11+, Edge 20.10240+ и Chrome 46+ (текущая версия).</span><span class="sxs-lookup"><span data-stu-id="60e0d-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="60e0d-111">Диспетчер статистики можно загрузить по ссылке [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) .</span><span class="sxs-lookup"><span data-stu-id="60e0d-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="60e0d-112">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="60e0d-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="60e0d-113">Развертывание диспетчера статистики</span><span class="sxs-lookup"><span data-stu-id="60e0d-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="60e0d-114">Устранение неполадок развертывания</span><span class="sxs-lookup"><span data-stu-id="60e0d-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="60e0d-115">Создание самозаверяемого сертификата</span><span class="sxs-lookup"><span data-stu-id="60e0d-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="60e0d-116">Развертывание диспетчера статистики</span><span class="sxs-lookup"><span data-stu-id="60e0d-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="60e0d-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="60e0d-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="60e0d-118">Чтобы развернуть диспетчер статистики, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60e0d-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="60e0d-119">Подготовьте хост-компьютер прослушиватель, установив систему кэша Redis в памяти и убедившись, что установлены соответствующие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="60e0d-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="60e0d-120">Установите службу прослушиватель на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="60e0d-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="60e0d-121">Установите веб-сайт на хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="60e0d-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="60e0d-122">Установите агент на каждом компьютере Skype для бизнеса Server, который вы хотите отслеживать.</span><span class="sxs-lookup"><span data-stu-id="60e0d-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="60e0d-123">Импорт топологии для отслеживаемого сервера.</span><span class="sxs-lookup"><span data-stu-id="60e0d-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="60e0d-124">Redis, служба прослушиватель и веб-сайт должны быть установлены на одном хост-компьютере.</span><span class="sxs-lookup"><span data-stu-id="60e0d-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="60e0d-125">Убедитесь, что на хост-компьютере не установлен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="60e0d-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="60e0d-126">Подготовка хост-компьютера прослушиватель</span><span class="sxs-lookup"><span data-stu-id="60e0d-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="60e0d-127">Чтобы подготовить хост-компьютер, необходимо установить систему кэша Redis в памяти и убедиться, что на компьютере есть действительный сертификат.</span><span class="sxs-lookup"><span data-stu-id="60e0d-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="60e0d-128">Корпорация Майкрософт рекомендует установить последнюю стабильную сборку Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="60e0d-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="60e0d-129">Диспетчер статистики версии 2.0 был протестирован с redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="60e0d-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="60e0d-130">Скачайте Redis со следующего сайта: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) .</span><span class="sxs-lookup"><span data-stu-id="60e0d-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="60e0d-131">Неподписаные установщики можно скачать с [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="60e0d-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="60e0d-132">При необходимости подписанные двадцатки доступны через популярных диспетчеров пакетов: [Nuget](https://www.nuget.org/packages/Redis-64/) и [TheClatey.](https://chocolatey.org/packages/redis-64)</span><span class="sxs-lookup"><span data-stu-id="60e0d-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="60e0d-133">Запустите предоставленный MSI и следуйте запросам.</span><span class="sxs-lookup"><span data-stu-id="60e0d-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="60e0d-134">Не добавляйте правило брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="60e0d-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="60e0d-135">Для службы прослушиватель требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="60e0d-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="60e0d-136">Корпорация Майкрософт настоятельно рекомендует иметь сертификат, подписанный доверенным органом сертификации.</span><span class="sxs-lookup"><span data-stu-id="60e0d-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="60e0d-137">Если вы хотите использовать самозаверя сертификат для тестирования в лаборатории, например, см. "Создание самозаверяемого [сертификата".](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="60e0d-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="60e0d-138">Обратите внимание, что агент использует проверку отпечатка сертификата (вместо проверки цепочки).</span><span class="sxs-lookup"><span data-stu-id="60e0d-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="60e0d-139">Он не будет делать полную проверку сертификатов, так как можно использовать самозаверяяние сертификатов.</span><span class="sxs-lookup"><span data-stu-id="60e0d-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="60e0d-140">Установка службы прослушиватель</span><span class="sxs-lookup"><span data-stu-id="60e0d-140">Install the Listener service</span></span>

<span data-ttu-id="60e0d-141">Установите службу прослушиватель на хост-компьютере, заведя StatsManPerfAgentListener.msi и указав следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="60e0d-142">Просмотрите лицензионный договор и, если вы согласны, выберите "Я принимаю условия лицензионного соглашения" и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="60e0d-143">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="60e0d-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="60e0d-144">**Пароль службы:** Это пароль, который удаленные агенты будут использовать для проверки подлинности в службе прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="60e0d-145">**Порт службы:** Это номер порта HTTPS, который прослушиватель будет использовать для связи с агентами.</span><span class="sxs-lookup"><span data-stu-id="60e0d-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="60e0d-146">Во время установки этот порт будет разрешен через локальный брандмауэр, будет создан ACL URL- и сертификат SSL будет привязан к этому порту.</span><span class="sxs-lookup"><span data-stu-id="60e0d-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="60e0d-147">Значение по умолчанию — 8443.</span><span class="sxs-lookup"><span data-stu-id="60e0d-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="60e0d-148">**Отпечаток сертификата:** Это отпечаток сертификата, который прослушиватель будет использовать для шифрования протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="60e0d-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="60e0d-149">У сетевой службы должен быть доступ на чтение закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="60e0d-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="60e0d-150">Нажмите **кнопку "Выбрать...",** чтобы выбрать отпечаток.</span><span class="sxs-lookup"><span data-stu-id="60e0d-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="60e0d-151">Отпечаток сертификата можно найти с помощью диспетчера сертификатов или с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="60e0d-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="60e0d-152">**Установите Dir:** Это каталог, в котором будут установлены binaries.</span><span class="sxs-lookup"><span data-stu-id="60e0d-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="60e0d-153">Вы можете изменить его по умолчанию с помощью кнопки **"Обзор...".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="60e0d-154">**Dir AppData:** Это каталог, в котором будут храниться папка Logs и другие данные.</span><span class="sxs-lookup"><span data-stu-id="60e0d-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="60e0d-155">Вы можете изменить его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60e0d-155">You may change it from the default.</span></span> <span data-ttu-id="60e0d-156">Он не будет удален при удалении.</span><span class="sxs-lookup"><span data-stu-id="60e0d-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="60e0d-157">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-157">Click **Install**.</span></span>
    
<span data-ttu-id="60e0d-158">Чтобы проверить установку, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="60e0d-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="60e0d-159">Откройте браузер и перейдите к https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="60e0d-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="60e0d-160">По умолчанию порт службы 8443 (если вы не указали другой порт).</span><span class="sxs-lookup"><span data-stu-id="60e0d-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="60e0d-161">Чтобы убедиться, что прослушиватель установлен правильно, наберем следующую:</span><span class="sxs-lookup"><span data-stu-id="60e0d-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="60e0d-162">Если появляется страница "Healthcheck", установка прослушиватель была успешной.</span><span class="sxs-lookup"><span data-stu-id="60e0d-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="60e0d-163">Если knownServerCount имеет 1 или более высокое, устанавливается подключение к Redis.</span><span class="sxs-lookup"><span data-stu-id="60e0d-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="60e0d-164">Пождав несколько минут и после установки хотя бы одного агента, убедитесь, что счетчик ValuesWritten приращен.</span><span class="sxs-lookup"><span data-stu-id="60e0d-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="60e0d-165">Установка веб-сайта</span><span class="sxs-lookup"><span data-stu-id="60e0d-165">Install the Website</span></span>

<span data-ttu-id="60e0d-166">Установите веб-сайт на хост-компьютере, задав StatsManWebSite.msi (включаемую в Skype для бизнеса [Server, диспетчер статистики Real-Time (64-битная)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)и указав следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="60e0d-167">Просмотрите лицензионный договор и, если вы согласны, выберите "Я принимаю условия лицензионного соглашения" и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="60e0d-168">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="60e0d-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="60e0d-169">**Порт службы:** Это номер порта, который будет прослушиваться веб-сайтом.</span><span class="sxs-lookup"><span data-stu-id="60e0d-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="60e0d-170">Вы можете изменить его позже с помощью привязки диспетчера IIS.</span><span class="sxs-lookup"><span data-stu-id="60e0d-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="60e0d-171">Во время установки этот порт будет разрешен через локальный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="60e0d-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="60e0d-172">**Установите Dir:** Это каталог, в котором будут установлены binaries.</span><span class="sxs-lookup"><span data-stu-id="60e0d-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="60e0d-173">Вы можете изменить его по умолчанию с помощью кнопки **"Обзор...".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="60e0d-174">**Dir AppData:** Это каталог, в котором будут храниться папка Logs и другие данные.</span><span class="sxs-lookup"><span data-stu-id="60e0d-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="60e0d-175">Вы можете изменить его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60e0d-175">You may change it from the default.</span></span> <span data-ttu-id="60e0d-176">Он не будет удален при удалении.</span><span class="sxs-lookup"><span data-stu-id="60e0d-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="60e0d-177">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-177">Click **Install**.</span></span>
    
<span data-ttu-id="60e0d-178">Чтобы просмотреть веб-сайт, откройте браузер и перейдите к: http://localhost ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="60e0d-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="60e0d-179">Чтобы просмотреть только сведения о здоровье, откройте браузер и перейдите к: http://localhost: \<webport\> /healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="60e0d-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="60e0d-180">По умолчанию номер веб-порта — 8080.</span><span class="sxs-lookup"><span data-stu-id="60e0d-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="60e0d-181">Привязку порта веб-сайта можно изменить с помощью диспетчера IIS.</span><span class="sxs-lookup"><span data-stu-id="60e0d-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="60e0d-182">Веб-установщик добавляет локализованную группу безопасности StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="60e0d-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="60e0d-183">Вы можете добавить учетные записи в эту группу безопасности, чтобы предоставить доступ к веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="60e0d-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="60e0d-184">Установка агентов</span><span class="sxs-lookup"><span data-stu-id="60e0d-184">Install the Agents</span></span>

<span data-ttu-id="60e0d-185">Установите агент на каждом сервере Skype для бизнеса Server, который вы хотите отслеживать, заверив StatsManPerfAgent.msi и указав следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="60e0d-186">Просмотрите лицензионный договор и, если вы согласны, выберите "Я принимаю условия лицензионного соглашения" и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="60e0d-187">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="60e0d-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="60e0d-188">**Пароль службы:** Это пароль, который удаленный агент будет использовать для проверки подлинности в службе прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="60e0d-189">**URI службы:** Это URI, где находится прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="60e0d-190">Он должен использовать https://name:port формат.</span><span class="sxs-lookup"><span data-stu-id="60e0d-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="60e0d-191">Можно использовать netBIOS-имя или FQDN.</span><span class="sxs-lookup"><span data-stu-id="60e0d-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="60e0d-192">Можно использовать имя, которое также указывается  в качестве субъекта или альтернативных имен субъектов сертификата в службе прослушиватель, но это не является требованием. </span><span class="sxs-lookup"><span data-stu-id="60e0d-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="60e0d-193">**Отпечаток службы:** Это отпечаток SSL-сертификата, который использует прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="60e0d-194">Агент будет использовать этот отпечаток для проверки подлинности прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="60e0d-195">(Он не будет делать полную проверку сертификатов, так как можно использовать самозаверяяние сертификатов.)</span><span class="sxs-lookup"><span data-stu-id="60e0d-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="60e0d-196">**Установите Dir:** Это каталог, в котором будут установлены binaries.</span><span class="sxs-lookup"><span data-stu-id="60e0d-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="60e0d-197">Вы можете изменить его по умолчанию с помощью кнопки **"Обзор...".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="60e0d-198">**Dir AppData:** Это каталог, в котором будут храниться папка Logs password.txt зашифрованный файл.</span><span class="sxs-lookup"><span data-stu-id="60e0d-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="60e0d-199">Вы можете благодарить за изменение значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60e0d-199">You may thanks change it from the default.</span></span> <span data-ttu-id="60e0d-200">Он не будет удален при удалении.</span><span class="sxs-lookup"><span data-stu-id="60e0d-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="60e0d-201">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-201">Click **Install**.</span></span>
    
<span data-ttu-id="60e0d-202">При установке агента на многочисленных компьютерах, скорее всего, это необходимо сделать в режиме без управления.</span><span class="sxs-lookup"><span data-stu-id="60e0d-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="60e0d-203">Например:</span><span class="sxs-lookup"><span data-stu-id="60e0d-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="60e0d-204">Импорт топологии</span><span class="sxs-lookup"><span data-stu-id="60e0d-204">Import the topology</span></span>
<span data-ttu-id="60e0d-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="60e0d-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="60e0d-206">После установки и запуска диспетчера статистики необходимо импортировать топологию Skype для бизнеса Server, чтобы диспетчер статистики знал сайт, пул и роль каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="60e0d-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="60e0d-207">Чтобы импортировать топологию Skype для бизнеса Server, используйте cmdlet [Get-CsPool,](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) чтобы получить сведения о каждом пуле, используемом в организации, а затем импортировать эти сведения в диспетчер статистики.</span><span class="sxs-lookup"><span data-stu-id="60e0d-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="60e0d-208">Чтобы импортировать топологию Skype для бизнеса Server, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60e0d-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="60e0d-209">На хост-сервере, где есть cmdlets PowerShell для Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="60e0d-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="60e0d-210">а.</span><span class="sxs-lookup"><span data-stu-id="60e0d-210">a.</span></span> <span data-ttu-id="60e0d-211">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="60e0d-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="60e0d-212">б.</span><span class="sxs-lookup"><span data-stu-id="60e0d-212">b.</span></span> <span data-ttu-id="60e0d-213">Скопируйте файл mypoolinfo.xml на сервер, на который работает прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="60e0d-214">На хост-сайте, где работает прослушиватель:</span><span class="sxs-lookup"><span data-stu-id="60e0d-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="60e0d-215">а.</span><span class="sxs-lookup"><span data-stu-id="60e0d-215">a.</span></span> <span data-ttu-id="60e0d-216">Запустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60e0d-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="60e0d-217">б.</span><span class="sxs-lookup"><span data-stu-id="60e0d-217">b.</span></span> <span data-ttu-id="60e0d-218">Перейдите в каталог, в котором установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="60e0d-219">Значение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="60e0d-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="60e0d-220">Чтобы подтвердить, какие серверы добавляются и обновляются, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="60e0d-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="60e0d-221">Следующая команда позволяет просматривать все параметры:</span><span class="sxs-lookup"><span data-stu-id="60e0d-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="60e0d-222">Чтобы увидеть импортируемые данные сервера, запустите следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="60e0d-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="60e0d-223">Если вы хотите отслеживать серверы, которые не находятся в топологии Skype для бизнеса Server (например, Exchange Server), вы можете импортировать один сервер на хост-сервер, на который работает прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="60e0d-224">Чтобы импортировать данные из одного сервера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60e0d-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="60e0d-225">Перейдите в каталог, в котором установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="60e0d-226">Значение по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="60e0d-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="60e0d-227">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="60e0d-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="60e0d-228">Устранение неполадок развертывания</span><span class="sxs-lookup"><span data-stu-id="60e0d-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="60e0d-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="60e0d-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="60e0d-230">Если агенту не удается запуститься, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="60e0d-231">Зарегистрирован ли агент в диспетчере статистики?</span><span class="sxs-lookup"><span data-stu-id="60e0d-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="60e0d-232">Убедитесь, что вы следовали инструкциям по импорту топологии.</span><span class="sxs-lookup"><span data-stu-id="60e0d-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="60e0d-233">См. ["Импорт топологии".](deploy.md#BKMK_ImportTopology)</span><span class="sxs-lookup"><span data-stu-id="60e0d-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="60e0d-234">Если агент находится на сервере, который не указан в топологии (например, узлы в кластере SQL AlwaysOn), вам потребуется добавить [](deploy.md#BKMK_ImportTopology)агент вручную, следуя инструкциям в импорте топологии.</span><span class="sxs-lookup"><span data-stu-id="60e0d-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="60e0d-235">Может ли агент связаться с прослушиватель?</span><span class="sxs-lookup"><span data-stu-id="60e0d-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="60e0d-236">Убедитесь, что служба прослушиватель запущена.</span><span class="sxs-lookup"><span data-stu-id="60e0d-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="60e0d-237">Если он не запущен, убедитесь, что Redis запущен, а затем попробуйте перезапустить прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="60e0d-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="60e0d-238">Убедитесь, что порт открыт для службы прослушиватель и компьютер агента может взаимодействовать с портом.</span><span class="sxs-lookup"><span data-stu-id="60e0d-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="60e0d-239">Чтобы убедиться, что диспетчер статистики собирает данные, можно проверить CSV-файл следующим образом.</span><span class="sxs-lookup"><span data-stu-id="60e0d-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="60e0d-240">Следующая команда извлекает имена хранилища счетчиков:</span><span class="sxs-lookup"><span data-stu-id="60e0d-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="60e0d-241">Следующая команда извлекает значения для указанных счетчиков:</span><span class="sxs-lookup"><span data-stu-id="60e0d-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="60e0d-242">Сведения обо всех событиях, которые можно увидеть в журнале событий приложений, см. в подсети "Устранение неполадок диспетчера статистики" в [Skype для бизнеса Server.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="60e0d-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="60e0d-243">Создание самозаверяемого сертификата</span><span class="sxs-lookup"><span data-stu-id="60e0d-243">Create a self-signed certificate</span></span>
<span data-ttu-id="60e0d-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="60e0d-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="60e0d-245">Корпорация Майкрософт настоятельно рекомендует использовать сертификат, подписанный доверенным органом сертификации.</span><span class="sxs-lookup"><span data-stu-id="60e0d-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="60e0d-246">Однако если вы хотите использовать самозаверя сертификат для тестирования, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="60e0d-247">Во время входа с учетной записи администратора в консоли PowerShell введите следующее:</span><span class="sxs-lookup"><span data-stu-id="60e0d-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="60e0d-248">Введите  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="60e0d-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="60e0d-249">Откроется диспетчер сертификатов для локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="60e0d-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="60e0d-250">Перейдите **в "Личное"** и откройте **"Сертификаты".**</span><span class="sxs-lookup"><span data-stu-id="60e0d-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="60e0d-251">Щелкните правой кнопкой **мыши StatsManListener \> — "Все задачи— \> управление закрытыми ключами"...**</span><span class="sxs-lookup"><span data-stu-id="60e0d-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="60e0d-252">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="60e0d-253">В поле **"Введите имена выбираемого** объекта" введите следующую: "Сетовая служба"</span><span class="sxs-lookup"><span data-stu-id="60e0d-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="60e0d-254">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="60e0d-255">В **области "Полный контроль"** отопустим этот **список.**</span><span class="sxs-lookup"><span data-stu-id="60e0d-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="60e0d-256">(Необходим только доступ на чтение.)</span><span class="sxs-lookup"><span data-stu-id="60e0d-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="60e0d-257">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="60e0d-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="60e0d-258">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="60e0d-258">For more information</span></span>
<span data-ttu-id="60e0d-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="60e0d-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="60e0d-260">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="60e0d-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="60e0d-261">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="60e0d-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="60e0d-262">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="60e0d-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="60e0d-263">[Устранение неполадок диспетчера статистики в Skype для бизнеса Server](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="60e0d-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>
