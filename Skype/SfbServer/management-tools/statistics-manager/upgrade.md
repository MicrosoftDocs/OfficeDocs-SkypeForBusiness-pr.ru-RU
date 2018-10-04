---
title: Обновление диспетчера статистики в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как обновление статистики Manager для Скайп для Business Server 2015.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374859"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="78a35-103">Обновление диспетчера статистики в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="78a35-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="78a35-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как обновление статистики Manager для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="78a35-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="78a35-105">В этом разделе описывается, как обновление существующей установки из диспетчера статистики для Скайп для Business Server — мощное средство, которое позволяет просматривать Скайп для данные о работоспособности и производительности Business Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="78a35-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="78a35-106">Опрос данные о производительности на серверах сотни раз в несколько секунд и просмотреть результаты мгновенно на веб-сайт диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="78a35-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="78a35-107">Дополнительные сведения о диспетчере статистики и новые возможности версии 1.1 содержатся в разделе [Планирование для диспетчера статистики для Скайп для Business Server 2015](plan.md) и [Развертывание диспетчера статистики для Скайп для Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="78a35-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="78a35-108">Сведения об известных проблемах, в выпуске 1.1 [Известные ошибки в выпуске 1.1](upgrade.md#BKMK_Fixed)см.</span><span class="sxs-lookup"><span data-stu-id="78a35-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="78a35-109">Предусмотрено два способа обновления:</span><span class="sxs-lookup"><span data-stu-id="78a35-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="78a35-110">**Автоматизированное обновление.**</span><span class="sxs-lookup"><span data-stu-id="78a35-110">**Automated upgrade.**</span></span> <span data-ttu-id="78a35-111">Этот метод используется автоматизированного сценария.</span><span class="sxs-lookup"><span data-stu-id="78a35-111">This method uses an automated script.</span></span> <span data-ttu-id="78a35-112">— Это самый простой метод и должны быть применены все сценарии обновления.</span><span class="sxs-lookup"><span data-stu-id="78a35-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="78a35-113">**Обновление вручную.**</span><span class="sxs-lookup"><span data-stu-id="78a35-113">**Manual upgrade.**</span></span> <span data-ttu-id="78a35-114">Этот метод предоставляется плана резервного копирования в случае нестандартный, который не удается выполнить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="78a35-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="78a35-115">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="78a35-115">Prerequisites</span></span>

<span data-ttu-id="78a35-116">Перед выполнением обновления убедитесь, чтобы у вас есть следующие данные:</span><span class="sxs-lookup"><span data-stu-id="78a35-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="78a35-117">Thumbprint активного сертификата прослушивателя</span><span class="sxs-lookup"><span data-stu-id="78a35-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="78a35-118">Пароль для службы прослушивателя (вводится при установке прослушивателя и каждого агента)</span><span class="sxs-lookup"><span data-stu-id="78a35-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="78a35-119">Конфигурация сертификата SSL для веб-сайта</span><span class="sxs-lookup"><span data-stu-id="78a35-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="78a35-120">Автоматизированное обновление</span><span class="sxs-lookup"><span data-stu-id="78a35-120">Automated upgrade</span></span>

<span data-ttu-id="78a35-121">Сценарий собирает текущие данные о сертификате и пароле для прослушивателя, удаляет предыдущую версию продукта и устанавливает новую.</span><span class="sxs-lookup"><span data-stu-id="78a35-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="78a35-122">Установленный на сервере экземпляр Redis остается без изменений, поэтому все данные, которые хранятся в кэше, будут сохранены при обновлении.</span><span class="sxs-lookup"><span data-stu-id="78a35-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="78a35-123">Разместите файлы MSI для новой версии агента, прослушиватель и веб-сайт вместе с сценария StatsMan.ps1 обновления в одной папке на компьютере прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="78a35-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="78a35-124">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78a35-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="78a35-125">Обновите компонент прослушивателя:</span><span class="sxs-lookup"><span data-stu-id="78a35-125">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="78a35-126">Во время его передачи программы установки в виде простого текста в командной строке отображается пароль службы диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="78a35-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="78a35-127">Убедитесь, что защитить монитора при необходимости.</span><span class="sxs-lookup"><span data-stu-id="78a35-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="78a35-128">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="78a35-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="78a35-129">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="78a35-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="78a35-130">Если служба прослушивателя работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="78a35-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="78a35-131">Разрешить приложению закрыть (служба была остановлена прослушиватель диспетчера статистики).</span><span class="sxs-lookup"><span data-stu-id="78a35-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="78a35-132">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="78a35-132">Continue the install process.</span></span> <span data-ttu-id="78a35-133">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="78a35-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="78a35-134">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="78a35-134">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="78a35-135">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78a35-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="78a35-136">Обновите компонент веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="78a35-136">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="78a35-137">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="78a35-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="78a35-138">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="78a35-138">Answer Yes.</span></span>
    
6. <span data-ttu-id="78a35-139">Если служба агента работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="78a35-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="78a35-140">Разрешите закрыть приложение (служба агента StatsMan будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="78a35-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="78a35-141">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="78a35-141">Continue the install process.</span></span> <span data-ttu-id="78a35-142">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="78a35-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="78a35-143">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="78a35-143">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="78a35-144">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78a35-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="78a35-145">Обновите компонент агента:</span><span class="sxs-lookup"><span data-stu-id="78a35-145">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="78a35-146">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="78a35-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="78a35-147">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="78a35-147">Answer Yes.</span></span>
    
10. <span data-ttu-id="78a35-148">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="78a35-148">Continue the install process.</span></span> <span data-ttu-id="78a35-149">Порт веб-сайта должен быть уже заполнен.</span><span class="sxs-lookup"><span data-stu-id="78a35-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="78a35-150">Если это не так, введите значение, которое вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="78a35-150">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="78a35-151">С помощью браузера проверьте правильность работы веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="78a35-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="78a35-152">Обновление агента можно использовать с параметром -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="78a35-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="78a35-153">Это обеспечит выполнение удаления и установки без запросов, позволив таким средствам, как PSExec, удаленно выполнять обновление на большом количестве серверов.</span><span class="sxs-lookup"><span data-stu-id="78a35-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="78a35-154">Обновление вручную</span><span class="sxs-lookup"><span data-stu-id="78a35-154">Manual upgrade</span></span>

<span data-ttu-id="78a35-155">Если по какой-либо причине автоматизированное обновление не удастся, можно выполнить обновление вручную следующим способом:</span><span class="sxs-lookup"><span data-stu-id="78a35-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="78a35-156">	На компьютере с прослушивателем удалите прослушиватель, веб-сайт и агент (если он был установлен на сервере) через элемент «Программы и компоненты» на панели управления.  </span><span class="sxs-lookup"><span data-stu-id="78a35-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="78a35-157"> Оставьте Redis, чтобы данные в кэше сохранились во время обновления.</span><span class="sxs-lookup"><span data-stu-id="78a35-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="78a35-p119">	Установите новые версии компонентов, при запросах указывая сохраненные ранее значения. Дополнительные сведения об установке компонентов см. в статье [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="78a35-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="78a35-160">Известные проблемы, исправленные в выпуске 1.1</span><span class="sxs-lookup"><span data-stu-id="78a35-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="78a35-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="78a35-161"></span></span>

<span data-ttu-id="78a35-162">В выпуске 1.1 исправлены следующие известные проблемы:</span><span class="sxs-lookup"><span data-stu-id="78a35-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="78a35-163">Пользовательского интерфейса или сервер/агента - многочисленные значительные надежность и производительность</span><span class="sxs-lookup"><span data-stu-id="78a35-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="78a35-164">Пользовательский Интерфейс - элемент управления фильтра Main теперь сортирует правильно с учетом (приводя людей, учитывайте определенных серверов не были в системе, когда они были)</span><span class="sxs-lookup"><span data-stu-id="78a35-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="78a35-165">Сервер — компоненты сервера теперь устанавливаются на серверах не на английском языке.</span><span class="sxs-lookup"><span data-stu-id="78a35-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="78a35-166">Сервер/агент — иногда компоненты агента и сервера не устанавливались, отображая ошибку .NET, из-за определенной версии .NET 4.0.</span><span class="sxs-lookup"><span data-stu-id="78a35-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="78a35-167">Эта проблема устранена.</span><span class="sxs-lookup"><span data-stu-id="78a35-167">This has been resolved.</span></span>
    
- <span data-ttu-id="78a35-168">-Расширенные агента ведения журнала событий, добавлена для агента StatsMan.</span><span class="sxs-lookup"><span data-stu-id="78a35-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="78a35-169">Агент больше не произойдет сбой при установке на сервере не в топологии, это будет регистрироваться в журнале событий, а также другие возможные условия ошибки.</span><span class="sxs-lookup"><span data-stu-id="78a35-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="78a35-170">Пользовательский Интерфейс — веб-клиентов с помощью браузера Chrome отображается несколько приглашения входа в систему при с помощью на клиентский компьютер не подключен к же рабочая группа или домен в качестве веб-Статистика диспетчера сервера.</span><span class="sxs-lookup"><span data-stu-id="78a35-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="78a35-171">Теперь требуется на сеанс следует указать только одного имени для входа.</span><span class="sxs-lookup"><span data-stu-id="78a35-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="78a35-172">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="78a35-172">For more information</span></span>
<span data-ttu-id="78a35-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="78a35-173"></span></span>

<span data-ttu-id="78a35-174">Дополнительные сведения приведены далее.</span><span class="sxs-lookup"><span data-stu-id="78a35-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="78a35-175">Планирование для диспетчера статистики для Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="78a35-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="78a35-176">Развертывание диспетчера статистики в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="78a35-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="78a35-177">Устранение проблем диспетчера статистики в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="78a35-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="78a35-178">Скайп для диспетчером сервера Статистика блога</span><span class="sxs-lookup"><span data-stu-id="78a35-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

