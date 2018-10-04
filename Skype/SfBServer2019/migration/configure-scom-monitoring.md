---
title: Настройка мониторинга SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После миграции на Скайп Microsoft для Business Server 2019, необходимо выполнить несколько задач для настройки Скайп для 2019 Business Server для работы с System Center Operations Manager.
ms.openlocfilehash: c54038bc89c62a9911e684e451a66f4f12a23124
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373744"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="fd88d-103">Настройка мониторинга SCOM</span><span class="sxs-lookup"><span data-stu-id="fd88d-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="fd88d-104">После миграции на Скайп для Business Server 2019, необходимо выполнить несколько задач для настройки Скайп для 2019 Business Server для работы с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fd88d-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="fd88d-105">Применение обновлений на сервере, выбранном для управления логикой централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="fd88d-106">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="fd88d-107">Настройте основной сервер управления System Center Operations Manager для переопределения кандидат центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="fd88d-108">Ниже приведены инструкции по выполнению каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="fd88d-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="fd88d-109">Применение обновлений на сервере, выбранном для управления логикой централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="fd88d-110">Выберите сервер, который имеет System Center Operations Manager файлы агента установлен и настроен как потенциальный узел обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="fd88d-111">Установка обновлений для данного сервера.</span><span class="sxs-lookup"><span data-stu-id="fd88d-111">Apply updates to this server.</span></span> <span data-ttu-id="fd88d-112">В разделе [Применить обновления](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="fd88d-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="fd88d-113">Обновите раздел реестра потенциального сервера централизованного обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="fd88d-114">На сервере, выбранном для управления логикой централизованного обнаружения откройте окно командной строки Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd88d-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="fd88d-115">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd88d-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="fd88d-116">При изменении реестра может возникнуть ошибка, которая не удалось выполнить команду, если раздел реестра уже существует.</span><span class="sxs-lookup"><span data-stu-id="fd88d-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="fd88d-117">При возникновении, можно игнорировать ошибки.</span><span class="sxs-lookup"><span data-stu-id="fd88d-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="fd88d-118">Настройте основной сервер управления System Center Operations Manager для переопределения узла-наблюдателя кандидат центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fd88d-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="fd88d-119">На компьютере, где была установлена консоль System Center Operations Manager разверните узел **Объекты пакета управления** и выберите **Обнаружение объектов**.</span><span class="sxs-lookup"><span data-stu-id="fd88d-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="fd88d-120">Нажмите кнопку **Изменить область**</span><span class="sxs-lookup"><span data-stu-id="fd88d-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="fd88d-121">На странице **Ориентация объектов пакета управления** выберите **LS Discovery Candidate**.</span><span class="sxs-lookup"><span data-stu-id="fd88d-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="fd88d-122">Переопределите **Эффективное значение LS Discovery Candidate** , имя сервера, выбранного в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="fd88d-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="fd88d-123">Чтобы завершить внесение изменений, перезапустите службу работоспособности на сервере управления корневой системы центр Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="fd88d-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

