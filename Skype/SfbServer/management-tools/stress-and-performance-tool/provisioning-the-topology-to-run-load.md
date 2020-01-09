---
title: Подготовка топологии для запуска загрузки в сценариях нагрузки и производительности
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: В Skype для бизнеса Server 2015 изменения или подготовка топологии, позволяющие пользователям успешно запускать средство "стресс и производительность".
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992496"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="39286-103">Подготовка топологии для запуска загрузки в сценариях нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="39286-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="39286-104">В Skype для бизнеса Server 2015 изменения или подготовка топологии, позволяющие пользователям успешно запускать средство "стресс и производительность".</span><span class="sxs-lookup"><span data-stu-id="39286-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="39286-105">В зависимости от существующих настроек и конфигурации для развертывания Skype для бизнеса Server 2015 может потребоваться внести некоторые изменения в свою среду.</span><span class="sxs-lookup"><span data-stu-id="39286-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="39286-106">Ниже перечислены эти изменения.</span><span class="sxs-lookup"><span data-stu-id="39286-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="39286-107">Установите для политики выполнения Windows PowerShell неограниченный доступ.</span><span class="sxs-lookup"><span data-stu-id="39286-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="39286-108">Если вы не уверены в том, что в данный момент установлено приложение, вы можете открыть командную консоль управления Skype для бизнеса Server и выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="39286-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="39286-109">Если значение "неограниченный" не возвращено, необходимо выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="39286-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="39286-110">Чтобы эффективно настроить Skype для бизнеса Server, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="39286-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="39286-111">Вы должны быть знакомы с топологией Skype для бизнеса Server 2015 (именами компьютеров, экземплярами служб, именами сайтов и политиками).</span><span class="sxs-lookup"><span data-stu-id="39286-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="39286-112">Назначьте некоторых пользователей, которые созданы для групп, например групп слежения группы ответа (например, URI SIP).</span><span class="sxs-lookup"><span data-stu-id="39286-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="39286-113">Чтобы запустить сценарий из командной строки, можно использовать:</span><span class="sxs-lookup"><span data-stu-id="39286-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="39286-114">Как правило, после того как вы запустите сценарий из этого пакета, полученные результаты будут храниться в файле в том же пути, из которого был выполнен сценарий.</span><span class="sxs-lookup"><span data-stu-id="39286-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="39286-115">Также есть формат именования, \<имя_сценария\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="39286-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="39286-116">Таким образом, если вы запустили Арчивингполици. ps1 на 12:15 PM, вы получите файл журнала с именем ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="39286-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="39286-117">Несмотря на то, что мы предоставили эти примеры для настройки сервера, вы можете как изменить конфигурацию, так и восстановить ее, после чего вы закончите выполнение нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="39286-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

