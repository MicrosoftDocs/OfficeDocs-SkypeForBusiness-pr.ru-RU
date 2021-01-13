---
title: Подготовка топологии для запуска нагрузки в сценариях stress и Performance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Изменения или подготовка топологии Skype для бизнеса Server 2015, позволяющие пользователям успешно запускать средство Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814939"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="052ff-103">Подготовка топологии для запуска нагрузки в сценариях stress и Performance</span><span class="sxs-lookup"><span data-stu-id="052ff-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="052ff-104">Изменения или подготовка топологии Skype для бизнеса Server 2015, позволяющие пользователям успешно запускать средство Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="052ff-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="052ff-105">В зависимости от существующих параметров и конфигурации развертывания Skype для бизнеса Server 2015 может потребоваться внести некоторые изменения в среду.</span><span class="sxs-lookup"><span data-stu-id="052ff-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="052ff-106">Ниже приводится список этих изменений.</span><span class="sxs-lookup"><span data-stu-id="052ff-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="052ff-107">Установите для Windows PowerShell выполнения неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="052ff-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="052ff-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span><span class="sxs-lookup"><span data-stu-id="052ff-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="052ff-109">Если значение Unrestricted не возвращается, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="052ff-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="052ff-110">Для эффективной настройки Skype для бизнеса Server необходимо:</span><span class="sxs-lookup"><span data-stu-id="052ff-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="052ff-111">Ознакомьтесь с топологией Skype для бизнеса Server 2015 (например, именами компьютеров, экземплярами служб, именами сайтов и политиками).</span><span class="sxs-lookup"><span data-stu-id="052ff-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="052ff-112">Назначьте некоторых пользователей, созданных группам, например группам ответа (например, SIP URIS).</span><span class="sxs-lookup"><span data-stu-id="052ff-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="052ff-113">Чтобы запустить сценарий из командной строки, можно использовать:</span><span class="sxs-lookup"><span data-stu-id="052ff-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="052ff-114">Как правило, после запуска сценария из этого пакета итоговые трассировки будут храниться в файле, который находится в том же пути, где был запускаться сценарий.</span><span class="sxs-lookup"><span data-stu-id="052ff-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="052ff-115">Также существует формат имен, \<scriptname\> $h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="052ff-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="052ff-116">Поэтому если вы запустили ArchivingPolicy.ps1 23:15, вы получите файл журнала с именем ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="052ff-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="052ff-117">Хотя мы предоставили эти примеры для конфигурации сервера, вы можете изменить конфигурацию и восстановить или откатить ее после завершения тестирования нагрузки.</span><span class="sxs-lookup"><span data-stu-id="052ff-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

