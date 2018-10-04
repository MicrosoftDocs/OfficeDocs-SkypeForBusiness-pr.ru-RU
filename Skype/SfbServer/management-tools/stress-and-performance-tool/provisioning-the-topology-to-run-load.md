---
title: Подготовка топологии для запуска нагрузки в сценарии нагрузка и производительность
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Скайп для изменения топологии Business Server 2015 или подготовки пользователи для успешного запуска средства нагрузка и производительность.
ms.openlocfilehash: 6ff08a3b99f4dc1f05b56c2a1fa86733ccf4f852
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373780"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="56236-103">Подготовка топологии для запуска нагрузки в сценарии нагрузка и производительность</span><span class="sxs-lookup"><span data-stu-id="56236-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="56236-104">Скайп для изменения топологии Business Server 2015 или подготовки пользователи для успешного запуска средства нагрузка и производительность.</span><span class="sxs-lookup"><span data-stu-id="56236-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="56236-105">В зависимости от существующих параметров и конфигурации для развертывания Скайп для Business Server 2015 может потребоваться внести изменения в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="56236-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="56236-106">Ниже приведен список этих изменений:</span><span class="sxs-lookup"><span data-stu-id="56236-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="56236-107">Задайте политику выполнения Windows PowerShell неограниченный.</span><span class="sxs-lookup"><span data-stu-id="56236-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="56236-108">Если вы не знаете его значение на данный момент можно откройте Скайп для Business Server Командная консоль и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56236-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="56236-109">Если не возвращаемое значение Unrestricted, то необходимо запустить этот следующим:</span><span class="sxs-lookup"><span data-stu-id="56236-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="56236-110">Чтобы эффективно настроить Скайп для Business Server, вам потребуется:</span><span class="sxs-lookup"><span data-stu-id="56236-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="56236-111">Ознакомиться с вашей Скайп для топологии Business Server 2015 (например, имена компьютеров, экземпляров служб, имена узлов и политики).</span><span class="sxs-lookup"><span data-stu-id="56236-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="56236-112">Назначьте некоторые пользователи, которые созданы в группы, например, группа ответа сервисные группы (например, коды URI SIP).</span><span class="sxs-lookup"><span data-stu-id="56236-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="56236-113">Чтобы запустить сценарий из командной строки, можно использовать:</span><span class="sxs-lookup"><span data-stu-id="56236-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="56236-114">Как правило после выполнения скрипта из этого пакета полученные трассировки будет храниться в файле в один и тот же путь из которых запуска сценария.</span><span class="sxs-lookup"><span data-stu-id="56236-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="56236-115">Существует формат именования, \<имя_сценария\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="56236-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="56236-116">Поэтому при запуске ArchivingPolicy.ps1 в 12:15 PM вы получите файл журнала с именем ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="56236-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="56236-117">Хотя мы подготовили в этих примерах конфигурации для сервера, он должен и изменение конфигурации и восстановления или откат после завершения выполнения нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="56236-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

