---
title: Настройка мониторинга SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После перехода на Microsoft Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.
ms.openlocfilehash: 098265f5b17ab4d25164495965b3d20a122f61fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239346"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="58e3d-103">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="58e3d-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="58e3d-104">После перехода на Skype для бизнеса Server 2019 необходимо выполнить несколько задач, чтобы настроить Skype для бизнеса Server 2019 для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="58e3d-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="58e3d-105">Примените обновления к серверу, выбранному для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="58e3d-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="58e3d-106">Обновите раздел реестра для основного сервера поиска кандидатов.</span><span class="sxs-lookup"><span data-stu-id="58e3d-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="58e3d-107">Настройка основного сервера System Center Operations Manager для переопределения узла центра обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="58e3d-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="58e3d-108">Ниже приведены инструкции по переносу каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="58e3d-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="58e3d-109">Примените обновления к серверу, выбранному для управления логикой центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="58e3d-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="58e3d-110">Выровняйте сервер, на котором установлены файлы агента System Center Operations Manager и настроен как узел обнаружения кандидатов.</span><span class="sxs-lookup"><span data-stu-id="58e3d-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="58e3d-111">Примените обновления к этому серверу.</span><span class="sxs-lookup"><span data-stu-id="58e3d-111">Apply updates to this server.</span></span> <span data-ttu-id="58e3d-112">Ознакомьтесь с разделом [применение обновлений](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="58e3d-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="58e3d-113">Обновите раздел реестра для основного сервера поиска кандидатов.</span><span class="sxs-lookup"><span data-stu-id="58e3d-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="58e3d-114">На сервере, выбранном для управления логикой центрального обнаружения, Откройте командное окно Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58e3d-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="58e3d-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="58e3d-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="58e3d-116">При внесении изменений в реестр может возникнуть сообщение о том, что команда завершилась сбоем, если раздел реестра уже существует.</span><span class="sxs-lookup"><span data-stu-id="58e3d-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="58e3d-117">Если вы столкнетесь с этим, вы можете спокойно проигнорировать ошибку.</span><span class="sxs-lookup"><span data-stu-id="58e3d-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="58e3d-118">Настройка основного сервера System Center Operations Manager для переопределения узла наблюдения за центральным обнаружением.</span><span class="sxs-lookup"><span data-stu-id="58e3d-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="58e3d-119">На компьютере с установленной консолью System Center Operations Manager разверните **объект пакета управления** , а затем выберите пункт **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="58e3d-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="58e3d-120">Выберите команду **изменить область**</span><span class="sxs-lookup"><span data-stu-id="58e3d-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="58e3d-121">На странице " **объекты пакета управления областью** " выберите **кандидат на обнаружение Ls**.</span><span class="sxs-lookup"><span data-stu-id="58e3d-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="58e3d-122">Переопределение **действующего значения-кандидата на обнаружение Ls** на имя сервера-кандидата, выбранное в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="58e3d-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="58e3d-123">Чтобы завершить изменения, перезапустите службу работоспособности на корневом сервере управления System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="58e3d-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

