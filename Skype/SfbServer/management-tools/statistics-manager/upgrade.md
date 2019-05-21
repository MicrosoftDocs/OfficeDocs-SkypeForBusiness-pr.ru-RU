---
title: Обновление диспетчера статистики в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы получить сведения о том, как обновить диспетчер статистики для Skype для бизнеса Server.'
ms.openlocfilehash: 70826776e9dfacdef75c7084a9aba6f4eede940a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299725"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="cb23e-103">Обновление диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb23e-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="cb23e-104">**Сводка:** В этой статье описано, как обновить диспетчер статистики для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="cb23e-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="cb23e-105">В этой статье описано, как обновить текущую установку диспетчера статистики для Skype для бизнеса Server — мощное средство, позволяющее просматривать данные о работоспособности и производительности Skype для бизнеса Server в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="cb23e-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="cb23e-106">Вы можете вести опрос данных о производительности нескольких сотен серверов каждые несколько секунд и мгновенно просматривать результаты на веб-сайте диспетчера статистики.</span><span class="sxs-lookup"><span data-stu-id="cb23e-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="cb23e-107">Дополнительные сведения об диспетчере статистики и новых возможностях в версии 2,0 можно найти в разделе [планирование диспетчера статистики для Skype для бизнеса Server](plan.md) и [Развертывание диспетчера статистики для Skype для бизнеса Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="cb23e-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="cb23e-108">Предусмотрено два способа обновления:</span><span class="sxs-lookup"><span data-stu-id="cb23e-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="cb23e-109">**Автоматизированное обновление.**</span><span class="sxs-lookup"><span data-stu-id="cb23e-109">**Automated upgrade.**</span></span> <span data-ttu-id="cb23e-110">Этот метод использует автоматический сценарий.</span><span class="sxs-lookup"><span data-stu-id="cb23e-110">This method uses an automated script.</span></span> <span data-ttu-id="cb23e-111">Это самый простой метод, который должен применяться ко всем сценариям обновления.</span><span class="sxs-lookup"><span data-stu-id="cb23e-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="cb23e-112">**Обновление вручную.**</span><span class="sxs-lookup"><span data-stu-id="cb23e-112">**Manual upgrade.**</span></span> <span data-ttu-id="cb23e-113">Этот метод предоставляется как резервный план в нетипичном случае, в котором происходит сбой автоматического обновления.</span><span class="sxs-lookup"><span data-stu-id="cb23e-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="cb23e-114">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="cb23e-114">Prerequisites</span></span>

<span data-ttu-id="cb23e-115">Перед выполнением обновления убедитесь, чтобы у вас есть следующие данные:</span><span class="sxs-lookup"><span data-stu-id="cb23e-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="cb23e-116">Thumbprint активного сертификата прослушивателя</span><span class="sxs-lookup"><span data-stu-id="cb23e-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="cb23e-117">Пароль для службы прослушивателя (вводится при установке прослушивателя и каждого агента)</span><span class="sxs-lookup"><span data-stu-id="cb23e-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="cb23e-118">Конфигурация сертификата SSL для веб-сайта</span><span class="sxs-lookup"><span data-stu-id="cb23e-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="cb23e-119">Автоматизированное обновление</span><span class="sxs-lookup"><span data-stu-id="cb23e-119">Automated upgrade</span></span>

<span data-ttu-id="cb23e-120">Сценарий собирает текущие данные о сертификате и пароле для прослушивателя, удаляет предыдущую версию продукта и устанавливает новую.</span><span class="sxs-lookup"><span data-stu-id="cb23e-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="cb23e-121">Установленный на сервере экземпляр Redis остается без изменений, поэтому все данные, которые хранятся в кэше, будут сохранены при обновлении.</span><span class="sxs-lookup"><span data-stu-id="cb23e-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="cb23e-122">Поместите файлы MSI для новой версии агента, прослушивателя и веб-сайта, а также сценарий Упдате-статсман. ps1 в одну папку на компьютере слушателя.</span><span class="sxs-lookup"><span data-stu-id="cb23e-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="cb23e-123">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb23e-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="cb23e-124">Обновите компонент прослушивателя:</span><span class="sxs-lookup"><span data-stu-id="cb23e-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="cb23e-125">Пароль службы диспетчера статистики будет отображаться в виде открытого текста в командной строке по мере его передачи в установщик.</span><span class="sxs-lookup"><span data-stu-id="cb23e-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="cb23e-126">Be sure to shield your monitor as needed.</span><span class="sxs-lookup"><span data-stu-id="cb23e-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="cb23e-127">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="cb23e-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="cb23e-128">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="cb23e-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="cb23e-129">Если служба прослушивателя работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="cb23e-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="cb23e-130">Разрешите приложению закрыть (служба прослушивания диспетчера статистики будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="cb23e-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="cb23e-131">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="cb23e-131">Continue the install process.</span></span> <span data-ttu-id="cb23e-132">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="cb23e-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="cb23e-133">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="cb23e-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="cb23e-134">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb23e-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="cb23e-135">Обновите компонент веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="cb23e-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="cb23e-136">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="cb23e-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="cb23e-137">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="cb23e-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="cb23e-138">Если служба агента работает, будет предложено закрыть приложение, чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="cb23e-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="cb23e-139">Разрешите закрыть приложение (служба агента StatsMan будет остановлена).</span><span class="sxs-lookup"><span data-stu-id="cb23e-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="cb23e-140">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="cb23e-140">Continue the install process.</span></span> <span data-ttu-id="cb23e-141">Пароль для службы и Thumbprint сертификата должны быть уже заполнены.</span><span class="sxs-lookup"><span data-stu-id="cb23e-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="cb23e-142">Если это не так, введите значения, которые вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="cb23e-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="cb23e-143">Откройте окно администрирования PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb23e-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="cb23e-144">Обновите компонент агента:</span><span class="sxs-lookup"><span data-stu-id="cb23e-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="cb23e-145">Во время выполнения сценария появится запрос на удаление предыдущей версии продукта.</span><span class="sxs-lookup"><span data-stu-id="cb23e-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="cb23e-146">Выберите «Да».</span><span class="sxs-lookup"><span data-stu-id="cb23e-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="cb23e-147">Продолжите процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="cb23e-147">Continue the install process.</span></span> <span data-ttu-id="cb23e-148">Порт веб-сайта должен быть уже заполнен.</span><span class="sxs-lookup"><span data-stu-id="cb23e-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="cb23e-149">Если это не так, введите значение, которое вы сохранили, а затем продолжите.</span><span class="sxs-lookup"><span data-stu-id="cb23e-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="cb23e-150">С помощью браузера проверьте правильность работы веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="cb23e-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cb23e-151">Обновление агента можно использовать с параметром -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="cb23e-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="cb23e-152">Это обеспечит выполнение удаления и установки без запросов, позволив таким средствам, как PSExec, удаленно выполнять обновление на большом количестве серверов.</span><span class="sxs-lookup"><span data-stu-id="cb23e-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="cb23e-153">Обновление вручную</span><span class="sxs-lookup"><span data-stu-id="cb23e-153">Manual upgrade</span></span>

<span data-ttu-id="cb23e-154">Если по какой-либо причине автоматизированное обновление не удастся, можно выполнить обновление вручную следующим способом:</span><span class="sxs-lookup"><span data-stu-id="cb23e-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="cb23e-155">	На компьютере с прослушивателем удалите прослушиватель, веб-сайт и агент (если он был установлен на сервере) через элемент «Программы и компоненты» на панели управления.  </span><span class="sxs-lookup"><span data-stu-id="cb23e-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="cb23e-156"> Оставьте Redis, чтобы данные в кэше сохранились во время обновления.</span><span class="sxs-lookup"><span data-stu-id="cb23e-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="cb23e-p118">	Установите новые версии компонентов, при запросах указывая сохраненные ранее значения. Дополнительные сведения об установке компонентов см. в статье [Развертывание диспетчера статистики](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="cb23e-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="cb23e-159">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="cb23e-159">For more information</span></span>
<span data-ttu-id="cb23e-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="cb23e-160"></span></span>

<span data-ttu-id="cb23e-161">Дополнительные сведения см. в указанных ниже статьях.</span><span class="sxs-lookup"><span data-stu-id="cb23e-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="cb23e-162">Планирование диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb23e-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="cb23e-163">Развертывание диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb23e-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="cb23e-164">Устранение проблем диспетчера статистики в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="cb23e-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
