---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После перехода на Microsoft Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754049"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="04cc6-103">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="04cc6-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="04cc6-104">После перехода на Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="04cc6-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="04cc6-105">Применение обновлений к серверу, который выбран для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="04cc6-106">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="04cc6-107">Настройте основной сервер управления System Center Operations Manager для переопределения кандидата центрального узла обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="04cc6-108">Инструкции по выполнению каждой задачи приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="04cc6-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="04cc6-109">Применение обновлений к серверу, который выбран для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="04cc6-110">Выберите сервер, на котором установлены файлы агента System Center Operations Manager и который настроен как потенциальный узел обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="04cc6-111">Применение обновлений к этому серверу.</span><span class="sxs-lookup"><span data-stu-id="04cc6-111">Apply updates to this server.</span></span> <span data-ttu-id="04cc6-112">См. раздел ["Применение обновлений".](apply-updates.md)</span><span class="sxs-lookup"><span data-stu-id="04cc6-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="04cc6-113">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="04cc6-114">На сервере, который выбран для управления логикой центрального обнаружения, откройте Windows PowerShell командной окне.</span><span class="sxs-lookup"><span data-stu-id="04cc6-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="04cc6-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="04cc6-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="04cc6-p102">При редактировании реестра может возникнуть ошибка выполнения команды, если раздел реестра уже существует. Эту ошибку можно игнорировать.</span><span class="sxs-lookup"><span data-stu-id="04cc6-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="04cc6-118">Настройте основной сервер управления System Center Operations Manager для переопределения узла-кандидата центрального узла-контрольщика обнаружения.</span><span class="sxs-lookup"><span data-stu-id="04cc6-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="04cc6-119">На компьютере с установленной консолью System Center Operations Manager разверните **Объекты пакета управления** и выберите **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="04cc6-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="04cc6-120">Щелкните **"Изменить область"**</span><span class="sxs-lookup"><span data-stu-id="04cc6-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="04cc6-121">на странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.</span><span class="sxs-lookup"><span data-stu-id="04cc6-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="04cc6-122">Переопределите **Эффективное значение LS Discovery Candidate**, указав имя сервера, выбранного ранее.</span><span class="sxs-lookup"><span data-stu-id="04cc6-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="04cc6-123">Чтобы донести изменения, перезапустите службу здравоохранения на корневом сервере управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="04cc6-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

