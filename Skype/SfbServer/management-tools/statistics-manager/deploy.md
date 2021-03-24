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
description: Сводка. Ознакомьтесь с этой темой, чтобы узнать, как развернуть диспетчер статистики для Skype для бизнеса Server.
ms.openlocfilehash: 406f4188347d32111bea4952815237b7f1015574
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105385"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="ad378-103">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ad378-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="ad378-104">**Сводка:** Ознакомьтесь с этой темой, чтобы узнать, как развернуть диспетчер статистики для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ad378-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="ad378-105">Диспетчер статистики для Skype для бизнеса Server — это мощный инструмент, позволяющий просматривать данные о работоспособности и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="ad378-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="ad378-106">Вы можете просматривать данные о производительности на сотнях серверов каждые несколько секунд и мгновенно просматривать результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="ad378-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="ad378-107">Прежде чем пытаться установить Диспетчер статистики, убедитесь, что вы знакомы с требованиями программного обеспечения, сетей и оборудования.</span><span class="sxs-lookup"><span data-stu-id="ad378-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="ad378-108">Дополнительные сведения см. в [проекте Plan for Statistics Manager for Skype for Business Server.](plan.md)</span><span class="sxs-lookup"><span data-stu-id="ad378-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ad378-109">Если вы обновляете предыдущую версию диспетчера статистики, см. в руб. Диспетчер статистики обновления [для Skype для бизнеса Server.](upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="ad378-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ad378-110">Веб-сайт диспетчера статистики был протестирован и работает правильно в Internet Explorer 11+, Edge 20.10240+ и Chrome 46+ (текущая вечнозеленая версия).</span><span class="sxs-lookup"><span data-stu-id="ad378-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="ad378-111">Вы можете найти диспетчер статистики, загружаемый по [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) ссылке .</span><span class="sxs-lookup"><span data-stu-id="ad378-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="ad378-112">В этом разделе содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="ad378-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="ad378-113">Диспетчер развертывания статистики</span><span class="sxs-lookup"><span data-stu-id="ad378-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="ad378-114">Устранение неполадок при развертывании</span><span class="sxs-lookup"><span data-stu-id="ad378-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="ad378-115">Создание самозаверяемого сертификата</span><span class="sxs-lookup"><span data-stu-id="ad378-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="ad378-116">Диспетчер развертывания статистики</span><span class="sxs-lookup"><span data-stu-id="ad378-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="ad378-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="ad378-117"><a name="BKMK_Deploy"> </a></span></span>

<span data-ttu-id="ad378-118">Чтобы развернуть диспетчер статистики, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad378-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="ad378-119">Подготовка хост-машины для прослушивания, установив систему кэшинга Redis в памяти и убедившись, что вы установили соответствующие сертификаты.</span><span class="sxs-lookup"><span data-stu-id="ad378-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="ad378-120">Установите службу прослушиватель на хост-машине.</span><span class="sxs-lookup"><span data-stu-id="ad378-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="ad378-121">Установите веб-сайт на хост-машине.</span><span class="sxs-lookup"><span data-stu-id="ad378-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="ad378-122">Установите агента на каждый компьютер Skype для бизнес-сервера, который вы хотите отслеживать.</span><span class="sxs-lookup"><span data-stu-id="ad378-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="ad378-123">Импорт топологии для отслеживаемого сервера.</span><span class="sxs-lookup"><span data-stu-id="ad378-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ad378-124">Redis, служба прослушиватель и веб-сайт должны быть установлены на одной и той же хост-машине.</span><span class="sxs-lookup"><span data-stu-id="ad378-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="ad378-125">Убедитесь, что на компьютере-хост-сервере не установлен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ad378-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="ad378-126">Подготовка хост-машины слушателя</span><span class="sxs-lookup"><span data-stu-id="ad378-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="ad378-127">Чтобы подготовить хост-машину, необходимо установить систему кэшинга Redis в памяти и убедиться, что на компьютере имеется действительный сертификат.</span><span class="sxs-lookup"><span data-stu-id="ad378-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="ad378-128">Корпорация Майкрософт рекомендует установить последнюю стабильную сборку Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="ad378-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="ad378-129">Диспетчер статистики версии 2.0 был протестирован с помощью Redis 3.2.100.</span><span class="sxs-lookup"><span data-stu-id="ad378-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="ad378-130">Скачайте Redis со следующего сайта: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) .</span><span class="sxs-lookup"><span data-stu-id="ad378-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="ad378-131">Неподписаные установщики можно скачать из [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="ad378-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="ad378-132">При необходимости подписанные биналоги доступны через популярных менеджеров пакетов: [Nuget](https://www.nuget.org/packages/Redis-64/) и [Choclatey.](https://chocolatey.org/packages/redis-64)</span><span class="sxs-lookup"><span data-stu-id="ad378-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="ad378-133">Запустите предоставленные msi и следуйте подсказкам.</span><span class="sxs-lookup"><span data-stu-id="ad378-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="ad378-134">Не проверяйте поле, чтобы добавить правило брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="ad378-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="ad378-135">Для службы "Прослушиватель" требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="ad378-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="ad378-136">Корпорация Майкрософт настоятельно рекомендует иметь сертификат, подписанный доверенным органом сертификата.</span><span class="sxs-lookup"><span data-stu-id="ad378-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="ad378-137">Если вы хотите использовать самозаверяемый сертификат для тестирования в лаборатории, например, см. в справке [Create a self-signed.](deploy.md#BKMK_SelfCert)</span><span class="sxs-lookup"><span data-stu-id="ad378-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="ad378-138">Обратите внимание, что агент использует проверку отпечатков пальцев сертификата (вместо проверки цепочки).</span><span class="sxs-lookup"><span data-stu-id="ad378-138">Note that the Agent uses certificate thumbprint verification (instead of chain verification).</span></span> <span data-ttu-id="ad378-139">Он не будет делать полную проверку сертификата, так как можно использовать самозаверяемые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="ad378-139">It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="ad378-140">Установка службы прослушиватель</span><span class="sxs-lookup"><span data-stu-id="ad378-140">Install the Listener service</span></span>

<span data-ttu-id="ad378-141">Установите службу listener на хост-компьютере, StatsManPerfAgentListener.msi и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="ad378-142">Просмотрите лицензионный договор, и если вы согласны, выберите я **принимаю** условия лицензионного соглашения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="ad378-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ad378-143">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ad378-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ad378-144">**Пароль службы:** Это пароль, который удаленные агенты будут использовать для проверки подлинности службы прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="ad378-145">**Порт службы:** Это номер порта HTTPS, который прослушиватель будет использовать для связи с агентами.</span><span class="sxs-lookup"><span data-stu-id="ad378-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="ad378-146">Во время установки этот порт будет разрешен через локальный брандмауэр, будет создан URL-адрес ACL и к этому порту будет привязан сертификат SSL.</span><span class="sxs-lookup"><span data-stu-id="ad378-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="ad378-147">По умолчанию — 8443.</span><span class="sxs-lookup"><span data-stu-id="ad378-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="ad378-148">**Отпечатки сертификатов:** Это отпечатки сертификатов, которые прослушиватель будет использовать для шифрования протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ad378-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="ad378-149">Служба сети должна иметь доступ к частному ключу для чтения.</span><span class="sxs-lookup"><span data-stu-id="ad378-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="ad378-150">Нажмите **кнопку Выберите ...**</span><span class="sxs-lookup"><span data-stu-id="ad378-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="ad378-151">Отпечатки пальцев сертификата можно найти с помощью диспетчера сертификатов или с помощью следующей команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad378-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - <span data-ttu-id="ad378-152">**Установка Dir:** Это каталог, в котором будут установлены биналоги.</span><span class="sxs-lookup"><span data-stu-id="ad378-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="ad378-153">Вы можете изменить его по умолчанию с помощью кнопки **Просмотр...**</span><span class="sxs-lookup"><span data-stu-id="ad378-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ad378-154">**Dir AppData:** Это каталог, в котором будут храниться папка журналов и другие данные.</span><span class="sxs-lookup"><span data-stu-id="ad378-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="ad378-155">Вы можете изменить его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad378-155">You may change it from the default.</span></span> <span data-ttu-id="ad378-156">Он не будет удален на удалении.</span><span class="sxs-lookup"><span data-stu-id="ad378-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ad378-157">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="ad378-157">Click **Install**.</span></span>
    
<span data-ttu-id="ad378-158">Чтобы проверить установку, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad378-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="ad378-159">Откройте браузер и перейдите в https://localhost: \<service-port\> /healthcheck/</span><span class="sxs-lookup"><span data-stu-id="ad378-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="ad378-160">По умолчанию порт службы составляет 8443 (если только вы не указали другой порт).</span><span class="sxs-lookup"><span data-stu-id="ad378-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="ad378-161">Чтобы обеспечить правильное установку прослушиватель, необходимо найти следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="ad378-162">Если страница healthcheck появляется, установка listener была успешной.</span><span class="sxs-lookup"><span data-stu-id="ad378-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="ad378-163">Если в knownServerCount 1 или выше установлено подключение к Redis.</span><span class="sxs-lookup"><span data-stu-id="ad378-163">If the KnownServerCount is 1 or higher,  the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="ad378-164">После ожидания нескольких минут и после установки хотя бы одного агента убедитесь, что счетчик ValuesWritten приращен.</span><span class="sxs-lookup"><span data-stu-id="ad378-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="ad378-165">Установка веб-сайта</span><span class="sxs-lookup"><span data-stu-id="ad378-165">Install the Website</span></span>

<span data-ttu-id="ad378-166">Установите веб-сайт на хост-машину, StatsManWebSite.msi с помощью Skype для бизнеса Server, Real-Time диспетчера статистики [(64-битный)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-166">Install the Website on the host machine by running the StatsManWebSite.msi (included with [Skype for Business Server, Real-Time Statistics Manager (64-bit)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) and specifying the following:</span></span>
  
1. <span data-ttu-id="ad378-167">Просмотрите лицензионный договор, и если вы согласны, выберите я **принимаю** условия лицензионного соглашения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="ad378-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ad378-168">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ad378-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ad378-169">**Порт службы:** Это номер порта, на который будет прослушиваться веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="ad378-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="ad378-170">Вы можете изменить его позже с помощью привязки диспетчера IIS.</span><span class="sxs-lookup"><span data-stu-id="ad378-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="ad378-171">Во время установки этот порт будет разрешен через локальный брандмауэр.</span><span class="sxs-lookup"><span data-stu-id="ad378-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="ad378-172">**Установка Dir:** Это каталог, в котором будут установлены binaries.</span><span class="sxs-lookup"><span data-stu-id="ad378-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="ad378-173">Вы можете изменить его по умолчанию с помощью кнопки **Просмотр...**</span><span class="sxs-lookup"><span data-stu-id="ad378-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ad378-174">**Dir AppData:** Это каталог, в котором будут храниться папка журналов и другие данные.</span><span class="sxs-lookup"><span data-stu-id="ad378-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="ad378-175">Вы можете изменить его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad378-175">You may change it from the default.</span></span> <span data-ttu-id="ad378-176">Он не будет удален на удалении.</span><span class="sxs-lookup"><span data-stu-id="ad378-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ad378-177">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="ad378-177">Click **Install**.</span></span>
    
<span data-ttu-id="ad378-178">Чтобы просмотреть веб-сайт, откройте браузер и перейдите по: http://localhost ,webport \> /.</span><span class="sxs-lookup"><span data-stu-id="ad378-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="ad378-179">Чтобы просмотреть только сведения о состоянии здоровья, откройте браузер и перейдите по: http://localhost: \<webport\> /healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="ad378-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="ad378-180">По умолчанию номер веб-порта — 8080.</span><span class="sxs-lookup"><span data-stu-id="ad378-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="ad378-181">Вы можете изменить привязку порта веб-сайта с помощью диспетчера IIS.</span><span class="sxs-lookup"><span data-stu-id="ad378-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="ad378-182">Веб-установщик добавляет локализованную группу безопасности под названием StatsManWebSiteUsers.</span><span class="sxs-lookup"><span data-stu-id="ad378-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="ad378-183">Вы можете добавить учетные записи в эту группу безопасности, чтобы предоставить доступ к веб-сайту.</span><span class="sxs-lookup"><span data-stu-id="ad378-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="ad378-184">Установка агентов</span><span class="sxs-lookup"><span data-stu-id="ad378-184">Install the Agents</span></span>

<span data-ttu-id="ad378-185">Установите агента на каждом сервере Skype для бизнеса, который вы хотите отслеживать, StatsManPerfAgent.msi и укажите следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="ad378-186">Просмотрите лицензионный договор, и если вы согласны, выберите я **принимаю** условия лицензионного соглашения, а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="ad378-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ad378-187">На следующей странице укажите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ad378-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ad378-188">**Пароль службы:** Это пароль, который будет использовать удаленный агент для проверки подлинности службы прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="ad378-189">**Служба URI:** Это URI, в котором находится слушатель.</span><span class="sxs-lookup"><span data-stu-id="ad378-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="ad378-190">Он должен использовать https://name:port формат.</span><span class="sxs-lookup"><span data-stu-id="ad378-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="ad378-191">Можно использовать имя NETBIOS или FQDN.</span><span class="sxs-lookup"><span data-stu-id="ad378-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="ad378-192">Вы можете использовать имя, которое также  указывается как тема или альтернативные имена субъекта сертификата в службе прослушиватель, но это не является требованием. </span><span class="sxs-lookup"><span data-stu-id="ad378-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="ad378-193">**Thumbprint службы:** Это отпечатки пальцев сертификата SSL, который используется слушателем.</span><span class="sxs-lookup"><span data-stu-id="ad378-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="ad378-194">Агент будет использовать этот отпечатки пальцев для проверки подлинности для слушателя.</span><span class="sxs-lookup"><span data-stu-id="ad378-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="ad378-195">(Он не будет делать полную проверку сертификата, так как можно использовать самозаверяемые сертификаты.)</span><span class="sxs-lookup"><span data-stu-id="ad378-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="ad378-196">**Установка Dir:** Это каталог, в котором будут установлены биналоги.</span><span class="sxs-lookup"><span data-stu-id="ad378-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="ad378-197">Вы можете изменить его по умолчанию с помощью кнопки **Просмотр...**</span><span class="sxs-lookup"><span data-stu-id="ad378-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ad378-198">**Dir AppData:** Это каталог, в котором будут храниться папка Журналы и зашифрованный password.txt файл.</span><span class="sxs-lookup"><span data-stu-id="ad378-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="ad378-199">Вы можете изменить его по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ad378-199">You may thanks change it from the default.</span></span> <span data-ttu-id="ad378-200">Он не будет удален на удалении.</span><span class="sxs-lookup"><span data-stu-id="ad378-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ad378-201">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="ad378-201">Click **Install**.</span></span>
    
<span data-ttu-id="ad378-202">Если вы устанавливаете агент на многочисленных машинах, вы, вероятно, захотите сделать это в без присмотра режиме.</span><span class="sxs-lookup"><span data-stu-id="ad378-202">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode.</span></span> <span data-ttu-id="ad378-203">Например:</span><span class="sxs-lookup"><span data-stu-id="ad378-203">For example:</span></span> 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="ad378-204">Импорт топологии</span><span class="sxs-lookup"><span data-stu-id="ad378-204">Import the topology</span></span>
<span data-ttu-id="ad378-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="ad378-205"><a name="BKMK_ImportTopology"> </a></span></span>

<span data-ttu-id="ad378-206">После установки и запуска диспетчера статистики необходимо импортировать топологию Skype для бизнеса Server, чтобы диспетчер статистики знал сайт, пул и роль каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="ad378-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="ad378-207">Чтобы импортировать топологию Skype для бизнеса Server, вы будете использовать команды [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) для получения сведений о каждом пуле, используемом в организации, а затем импортировать эти сведения в Диспетчер статистики.</span><span class="sxs-lookup"><span data-stu-id="ad378-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="ad378-208">Чтобы импортировать топологию Skype для бизнеса Server, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad378-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="ad378-209">На хосте, который имеет cmdlets Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad378-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="ad378-210">а)</span><span class="sxs-lookup"><span data-stu-id="ad378-210">a.</span></span> <span data-ttu-id="ad378-211">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad378-211">Run the following command:</span></span> 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="ad378-212">б)</span><span class="sxs-lookup"><span data-stu-id="ad378-212">b.</span></span> <span data-ttu-id="ad378-213">Скопируйте файл "mypoolinfo.xml" на сервер, на который выполняется прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="ad378-214">На хосте, который запускает прослушиватель:</span><span class="sxs-lookup"><span data-stu-id="ad378-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="ad378-215">а)</span><span class="sxs-lookup"><span data-stu-id="ad378-215">a.</span></span> <span data-ttu-id="ad378-216">Запустите PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad378-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="ad378-217">б)</span><span class="sxs-lookup"><span data-stu-id="ad378-217">b.</span></span> <span data-ttu-id="ad378-218">Перейдите к каталогу, в котором установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="ad378-219">По умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ad378-219">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="ad378-220">Чтобы подтвердить, какие серверы добавляются и обновляются, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad378-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="ad378-221">Следующая команда позволяет просматривать все параметры:</span><span class="sxs-lookup"><span data-stu-id="ad378-221">The following command enables you to view all options:</span></span>
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="ad378-222">Чтобы увидеть импортируемые данные сервера, запустите следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="ad378-222">To see your currently imported server information, run the following script:</span></span> 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="ad378-223">Если вы хотите отслеживать серверы, которые не находятся в топологии Skype для бизнес-сервера Exchange Server, например, вы можете импортировать один сервер на хосте, который управляет прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="ad378-224">Чтобы импортировать один сервер, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ad378-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="ad378-225">Перейдите к каталогу, в котором установлен прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="ad378-226">По умолчанию:</span><span class="sxs-lookup"><span data-stu-id="ad378-226">The default is:</span></span> 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="ad378-227">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad378-227">Run the following command:</span></span>
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="ad378-228">Устранение неполадок при развертывании</span><span class="sxs-lookup"><span data-stu-id="ad378-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="ad378-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="ad378-229"><a name="BKMK_Troubleshoot"> </a></span></span>

<span data-ttu-id="ad378-230">Если агент не запустится, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="ad378-231">Зарегистрирован ли агент в диспетчере статистики?</span><span class="sxs-lookup"><span data-stu-id="ad378-231">Is the agent registered in Statistics Manager?</span></span>
    
    1. <span data-ttu-id="ad378-232">Убедитесь, что вы следовали инструкциям по импорту топологии.</span><span class="sxs-lookup"><span data-stu-id="ad378-232">Make sure you followed the instructions for importing the topology.</span></span> <span data-ttu-id="ad378-233">См. [в этой ленте](deploy.md#BKMK_ImportTopology)Импорт топологии .</span><span class="sxs-lookup"><span data-stu-id="ad378-233">See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
        
    2. <span data-ttu-id="ad378-234">Если агент находится на сервере, который не указан в топологии (например, узлы в кластере SQL AlwaysOn), необходимо добавить агент вручную, следуя инструкциям в [Импорт](deploy.md#BKMK_ImportTopology)топологии .</span><span class="sxs-lookup"><span data-stu-id="ad378-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="ad378-235">Может ли агент связаться с слушателем?</span><span class="sxs-lookup"><span data-stu-id="ad378-235">Can the Agent contact the Listener?</span></span>
    
    1. <span data-ttu-id="ad378-236">Убедитесь, что служба прослушиватель запущена.</span><span class="sxs-lookup"><span data-stu-id="ad378-236">Make sure the Listener service is running.</span></span> 
        
        <span data-ttu-id="ad378-237">Если он не запущен, убедитесь, что Redis запущен, а затем попробуйте перезапустить прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="ad378-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
        
    2. <span data-ttu-id="ad378-238">Убедитесь, что порт открыт для службы прослушивания и что компьютер Agent может взаимодействовать с портом.</span><span class="sxs-lookup"><span data-stu-id="ad378-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="ad378-239">Чтобы убедиться, что диспетчер статистики собирает данные, вы можете проверить файл CSV следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad378-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="ad378-240">Следующая команда извлекает имена счетчика хранения:</span><span class="sxs-lookup"><span data-stu-id="ad378-240">The following command retrieves the counter storage names:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="ad378-241">Следующая команда извлекает значения для указанных счетчиков:</span><span class="sxs-lookup"><span data-stu-id="ad378-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="ad378-242">Сведения обо всех событиях, которые можно увидеть в журнале событий приложения, см. в статью Диспетчер статистики устранения неполадок [для Skype для бизнеса Server.](troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="ad378-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="ad378-243">Создание самозаверяемого сертификата</span><span class="sxs-lookup"><span data-stu-id="ad378-243">Create a self-signed certificate</span></span>
<span data-ttu-id="ad378-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="ad378-244"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="ad378-245">Корпорация Майкрософт настоятельно рекомендует использовать сертификат, подписанный доверенным органом сертификата.</span><span class="sxs-lookup"><span data-stu-id="ad378-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="ad378-246">Однако, если вы хотите использовать самозаверяется сертификат для тестирования, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="ad378-247">На консоли PowerShell во время входа в качестве администратора введите следующее:</span><span class="sxs-lookup"><span data-stu-id="ad378-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="ad378-248">Введите  `certlm.msc` .</span><span class="sxs-lookup"><span data-stu-id="ad378-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="ad378-249">Это откроет диспетчер сертификатов для локальной машины.</span><span class="sxs-lookup"><span data-stu-id="ad378-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="ad378-250">Перейдите к **Персональным,** а затем откройте **сертификаты.**</span><span class="sxs-lookup"><span data-stu-id="ad378-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="ad378-251">Правой кнопкой мыши **на statsManListener- \> Все задачи- Управление \> закрытыми ключами ...**</span><span class="sxs-lookup"><span data-stu-id="ad378-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="ad378-252">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ad378-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="ad378-253">В **введите имена объектов, чтобы выбрать поле,** введите следующее: Network Service</span><span class="sxs-lookup"><span data-stu-id="ad378-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="ad378-254">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad378-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="ad378-255">Под **полным контролем** отойте проверку **допустимого** чека.</span><span class="sxs-lookup"><span data-stu-id="ad378-255">Under **Full Control**, un-check the **Allow** check box.</span></span> <span data-ttu-id="ad378-256">(Необходим только доступ к считыву.)</span><span class="sxs-lookup"><span data-stu-id="ad378-256">(Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="ad378-257">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad378-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="ad378-258">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ad378-258">For more information</span></span>
<span data-ttu-id="ad378-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="ad378-259"><a name="BKMK_SelfCert"> </a></span></span>

<span data-ttu-id="ad378-260">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="ad378-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="ad378-261">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ad378-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="ad378-262">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ad378-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- <span data-ttu-id="ad378-263">[Диспетчер статистики устранения неполадок для Skype для бизнеса Server](troubleshoot.md) ß</span><span class="sxs-lookup"><span data-stu-id="ad378-263">[Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md) ß</span></span>