---
title: Обновление диспетчера статистики в Skype для бизнеса Server
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
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: Сводка. В этом разделе вы узнаете, как обновить диспетчер статистики для Skype для бизнеса Server.
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821769"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="3050b-103">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3050b-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="3050b-104">**Сводка:** В этом разделе вы узнаете, как обновить диспетчер статистики для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3050b-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="3050b-105">В этом разделе описывается обновление существующей установки диспетчера статистики для Skype для бизнеса Server — мощного средства, которое позволяет просматривать данные о работоспособности и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="3050b-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="3050b-106">Вы можете опросить данные о производительности на нескольких сотнях серверов каждые несколько секунд и мгновенно просмотреть результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="3050b-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="3050b-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and Deploy [Statistics Manager for Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="3050b-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="3050b-108">Существует два способа обновления:</span><span class="sxs-lookup"><span data-stu-id="3050b-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="3050b-109">**Автоматическое обновление.**</span><span class="sxs-lookup"><span data-stu-id="3050b-109">**Automated upgrade.**</span></span> <span data-ttu-id="3050b-110">Этот метод использует автоматический сценарий.</span><span class="sxs-lookup"><span data-stu-id="3050b-110">This method uses an automated script.</span></span> <span data-ttu-id="3050b-111">Это самый простой метод, который должен применяться во всех сценариях обновления.</span><span class="sxs-lookup"><span data-stu-id="3050b-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="3050b-112">**Обновление вручную.**</span><span class="sxs-lookup"><span data-stu-id="3050b-112">**Manual upgrade.**</span></span> <span data-ttu-id="3050b-113">Этот метод предоставляется в качестве плана резервного копирования в случае нестандартного сбойного автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="3050b-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="3050b-114">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="3050b-114">Prerequisites</span></span>

<span data-ttu-id="3050b-115">Перед обновлением убедитесь, что у вас есть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="3050b-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="3050b-116">Отпечаток сертификата активного прослушиватель</span><span class="sxs-lookup"><span data-stu-id="3050b-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="3050b-117">Пароль службы прослушиватель (введен при установке прослушиватель и каждого агента)</span><span class="sxs-lookup"><span data-stu-id="3050b-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="3050b-118">Настройка SSL-сертификата для веб-сайта</span><span class="sxs-lookup"><span data-stu-id="3050b-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="3050b-119">Автоматическое обновление</span><span class="sxs-lookup"><span data-stu-id="3050b-119">Automated upgrade</span></span>

<span data-ttu-id="3050b-120">Сценарий соберет текущие сведения о сертификате и пароль прослушиватель, установит старую версию продукта, а затем установит новую версию продукта.</span><span class="sxs-lookup"><span data-stu-id="3050b-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="3050b-121">Экземпляр Redis, установленный на сервере, не будет затронут, поэтому все данные, хранимые в кэше, будут сохранены в процессе обновления.</span><span class="sxs-lookup"><span data-stu-id="3050b-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="3050b-122">Поместите MSI-файлы для новой версии агента, прослушиватель и веб-сайта вместе с сценарием Update-StatsMan.ps1 в одну папку на компьютере прослушиватель.</span><span class="sxs-lookup"><span data-stu-id="3050b-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="3050b-123">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3050b-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="3050b-124">Обновим компонент прослушиватель:</span><span class="sxs-lookup"><span data-stu-id="3050b-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="3050b-125">Пароль службы диспетчера статистики будет отображаться в командной строке в виде простого текста, передав его установщику.</span><span class="sxs-lookup"><span data-stu-id="3050b-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="3050b-126">Обязательно экранировать монитор при необходимости.</span><span class="sxs-lookup"><span data-stu-id="3050b-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="3050b-127">При запуске сценария вам будет предложено удалить старую версию продукта.</span><span class="sxs-lookup"><span data-stu-id="3050b-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="3050b-128">Ответ "Да".</span><span class="sxs-lookup"><span data-stu-id="3050b-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="3050b-129">Если служба прослушиватель запущена, перед продолжением вам будет предложено закрыть приложение.</span><span class="sxs-lookup"><span data-stu-id="3050b-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="3050b-130">Разрешить закрыть приложение (служба прослушиватель диспетчера статистики будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="3050b-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="3050b-131">Продолжите процесс установки.</span><span class="sxs-lookup"><span data-stu-id="3050b-131">Continue the install process.</span></span> <span data-ttu-id="3050b-132">Следует заметить, что пароль службы и отпечаток сертификата предварительно заполнены.</span><span class="sxs-lookup"><span data-stu-id="3050b-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="3050b-133">Если нет, добавьте сохраненные значения, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="3050b-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="3050b-134">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3050b-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="3050b-135">Обновим компонент веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="3050b-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="3050b-136">При запуске сценария вам будет предложено удалить старую версию продукта.</span><span class="sxs-lookup"><span data-stu-id="3050b-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="3050b-137">Ответ "Да".</span><span class="sxs-lookup"><span data-stu-id="3050b-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="3050b-138">Если служба агента запущена, перед продолжением вам будет предложено закрыть приложение.</span><span class="sxs-lookup"><span data-stu-id="3050b-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="3050b-139">Разрешить закрыть приложение (служба агента StatsMan будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="3050b-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="3050b-140">Продолжите процесс установки.</span><span class="sxs-lookup"><span data-stu-id="3050b-140">Continue the install process.</span></span> <span data-ttu-id="3050b-141">Следует заметить, что пароль службы и отпечаток сертификата предварительно заполнены.</span><span class="sxs-lookup"><span data-stu-id="3050b-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="3050b-142">Если нет, добавьте сохраненные значения, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="3050b-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="3050b-143">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3050b-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="3050b-144">Обновив компонент агента:</span><span class="sxs-lookup"><span data-stu-id="3050b-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="3050b-145">При запуске сценария вам будет предложено удалить старую версию продукта.</span><span class="sxs-lookup"><span data-stu-id="3050b-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="3050b-146">Ответ "Да".</span><span class="sxs-lookup"><span data-stu-id="3050b-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="3050b-147">Продолжите процесс установки.</span><span class="sxs-lookup"><span data-stu-id="3050b-147">Continue the install process.</span></span> <span data-ttu-id="3050b-148">Обратите внимание, что порт веб-сайта предварительно заполнен.</span><span class="sxs-lookup"><span data-stu-id="3050b-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="3050b-149">Если нет, добавьте сохраненные значения, прежде чем продолжить.</span><span class="sxs-lookup"><span data-stu-id="3050b-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="3050b-150">Убедитесь, что веб-сайт работает как ожидается, с помощью браузера.</span><span class="sxs-lookup"><span data-stu-id="3050b-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3050b-151">Обновление агента можно использовать с переключателем -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="3050b-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="3050b-152">Это позволит процессу удалений и установки запускаться в тихом режиме, что позволяет таким средствам, как PSExec, удаленно запускать обновление на большом количестве серверов.</span><span class="sxs-lookup"><span data-stu-id="3050b-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="3050b-153">Обновление вручную</span><span class="sxs-lookup"><span data-stu-id="3050b-153">Manual upgrade</span></span>

<span data-ttu-id="3050b-154">Если по какой-либо причине автоматическое обновление не выполняется, всегда можно выполнить обновление вручную следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3050b-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="3050b-155">На компьютере прослушиватель можно удалить прослушиватель, веб-сайт и агент (если он был установлен на этом сервере) с помощью панели управления программ и компонентов.</span><span class="sxs-lookup"><span data-stu-id="3050b-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="3050b-156">Храните Redis установленным, чтобы данные в кэше затем сохранялась в процессе обновления.</span><span class="sxs-lookup"><span data-stu-id="3050b-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="3050b-157">Установите новые версии компонентов, в том числе сохраненные выше значения при их запросе.</span><span class="sxs-lookup"><span data-stu-id="3050b-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="3050b-158">Дополнительные сведения об установке компонентов см. в [диспетчере развертывания статистики](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="3050b-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="3050b-159">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3050b-159">For more information</span></span>
<span data-ttu-id="3050b-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="3050b-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="3050b-161">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="3050b-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="3050b-162">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3050b-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="3050b-163">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3050b-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="3050b-164">Устранение проблем диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3050b-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
