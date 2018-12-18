---
title: Обновление статистики Manager для Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как обновление статистики Manager для Скайп для Business Server.'
ms.openlocfilehash: e2118377fc782af6818d070bc0bd3f5ddacab99e
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297897"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="21a1f-103">Обновление статистики Manager для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="21a1f-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="21a1f-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как обновление статистики Manager для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="21a1f-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="21a1f-105">В этом разделе описывается, как обновление существующей установки из диспетчера статистики для Скайп для Business Server — мощное средство, которое позволяет просматривать Скайп для данные о работоспособности и производительности Business Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="21a1f-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="21a1f-106">Опрос данные о производительности на серверах сотни раз в несколько секунд и просмотреть результаты мгновенно на веб-сайт диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="21a1f-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="21a1f-107">Дополнительные сведения о диспетчере статистики и новые возможности в версии 2.0 [для диспетчера статистики для Скайп для Business Server планирование](plan.md) и [Развертывание диспетчера статистики для Скайп для Business Server](deploy.md)см.</span><span class="sxs-lookup"><span data-stu-id="21a1f-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="21a1f-108">Предусмотрено два способа обновления:</span><span class="sxs-lookup"><span data-stu-id="21a1f-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="21a1f-109">**Автоматизированное обновление.**</span><span class="sxs-lookup"><span data-stu-id="21a1f-109">**Automated upgrade.**</span></span> <span data-ttu-id="21a1f-110">Этот метод используется автоматизированного сценария.</span><span class="sxs-lookup"><span data-stu-id="21a1f-110">This method uses an automated script.</span></span> <span data-ttu-id="21a1f-111">— Это самый простой метод и должны быть применены все сценарии обновления.</span><span class="sxs-lookup"><span data-stu-id="21a1f-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="21a1f-112">**Обновление вручную.**</span><span class="sxs-lookup"><span data-stu-id="21a1f-112">**Manual upgrade.**</span></span> <span data-ttu-id="21a1f-113">Этот метод предоставляется плана резервного копирования в случае нестандартный, который не удается выполнить автоматическое обновление.</span><span class="sxs-lookup"><span data-stu-id="21a1f-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="21a1f-114">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="21a1f-114">Prerequisites</span></span>

<span data-ttu-id="21a1f-115">Перед выполнением обновления убедитесь, чтобы у вас есть следующие данные:</span><span class="sxs-lookup"><span data-stu-id="21a1f-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="21a1f-116">Thumbprint активного сертификата прослушивателя</span><span class="sxs-lookup"><span data-stu-id="21a1f-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="21a1f-117">Пароль для службы прослушивателя (вводится при установке прослушивателя и каждого агента)</span><span class="sxs-lookup"><span data-stu-id="21a1f-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="21a1f-118">Конфигурация сертификата SSL для веб-сайта</span><span class="sxs-lookup"><span data-stu-id="21a1f-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="21a1f-119">Автоматизированное обновление</span><span class="sxs-lookup"><span data-stu-id="21a1f-119">Automated upgrade</span></span>

<span data-ttu-id="21a1f-120">Сценарий собирает текущие данные о сертификате и пароле для прослушивателя, удаляет предыдущую версию продукта и устанавливает новую.</span><span class="sxs-lookup"><span data-stu-id="21a1f-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="21a1f-121">Установленный на сервере экземпляр Redis остается без изменений, поэтому все данные, которые хранятся в кэше, будут сохранены при обновлении.</span><span class="sxs-lookup"><span data-stu-id="21a1f-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="21a1f-122">Разместите файлы MSI для новой версии агента, прослушиватель и веб-сайт вместе с сценария StatsMan.ps1 обновления в одной папке на компьютере прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="21a1f-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="21a1f-123">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21a1f-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="21a1f-124">Обновите компонент прослушивателя:</span><span class="sxs-lookup"><span data-stu-id="21a1f-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="21a1f-125">Во время его передачи программы установки в виде простого текста в командной строке отображается пароль службы диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="21a1f-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="21a1f-126">Be sure to shield your monitor as needed.</span><span class="sxs-lookup"><span data-stu-id="21a1f-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="21a1f-127">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="21a1f-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="21a1f-128">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="21a1f-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="21a1f-129">Если служба прослушивателя работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="21a1f-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="21a1f-130">Разрешить приложению закрыть (служба была остановлена прослушиватель диспетчера статистики).</span><span class="sxs-lookup"><span data-stu-id="21a1f-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="21a1f-131">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="21a1f-131">Continue the install process.</span></span> <span data-ttu-id="21a1f-132">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="21a1f-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="21a1f-133">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="21a1f-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="21a1f-134">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21a1f-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="21a1f-135">Обновите компонент веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="21a1f-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="21a1f-136">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="21a1f-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="21a1f-137">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="21a1f-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="21a1f-138">Если служба агента работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="21a1f-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="21a1f-139">Разрешите закрыть приложение (служба агента StatsMan будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="21a1f-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="21a1f-140">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="21a1f-140">Continue the install process.</span></span> <span data-ttu-id="21a1f-141">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="21a1f-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="21a1f-142">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="21a1f-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="21a1f-143">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21a1f-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="21a1f-144">Обновите компонент агента:</span><span class="sxs-lookup"><span data-stu-id="21a1f-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="21a1f-145">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="21a1f-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="21a1f-146">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="21a1f-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="21a1f-147">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="21a1f-147">Continue the install process.</span></span> <span data-ttu-id="21a1f-148">Порт веб-сайта должен быть уже заполнен.</span><span class="sxs-lookup"><span data-stu-id="21a1f-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="21a1f-149">Если это не так, введите значение, которое вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="21a1f-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="21a1f-150">С помощью браузера проверьте правильность работы веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="21a1f-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="21a1f-151">Обновление агента можно использовать с параметром -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="21a1f-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="21a1f-152">Это обеспечит выполнение удаления и установки без запросов, позволив таким средствам, как PSExec, удаленно выполнять обновление на большом количестве серверов.</span><span class="sxs-lookup"><span data-stu-id="21a1f-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="21a1f-153">Обновление вручную</span><span class="sxs-lookup"><span data-stu-id="21a1f-153">Manual upgrade</span></span>

<span data-ttu-id="21a1f-154">Если по какой-либо причине автоматизированное обновление не удастся, можно выполнить обновление вручную следующим способом:</span><span class="sxs-lookup"><span data-stu-id="21a1f-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="21a1f-155">	На компьютере с прослушивателем удалите прослушиватель, веб-сайт и агент (если он был установлен на сервере) через элемент «Программы и компоненты» на панели управления.  </span><span class="sxs-lookup"><span data-stu-id="21a1f-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="21a1f-156"> Оставьте Redis, чтобы данные в кэше сохранились во время обновления.</span><span class="sxs-lookup"><span data-stu-id="21a1f-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="21a1f-p118">	Установите новые версии компонентов, при запросах указывая сохраненные ранее значения. Дополнительные сведения об установке компонентов см. в статье [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="21a1f-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="21a1f-159">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="21a1f-159">For more information</span></span>
<span data-ttu-id="21a1f-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="21a1f-160"></span></span>

<span data-ttu-id="21a1f-161">Дополнительные сведения приведены далее.</span><span class="sxs-lookup"><span data-stu-id="21a1f-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="21a1f-162">Планирование для диспетчера статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="21a1f-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="21a1f-163">Развертывание диспетчера статистики для Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="21a1f-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="21a1f-164">Устранение неполадок в диспетчер статистики для Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="21a1f-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
