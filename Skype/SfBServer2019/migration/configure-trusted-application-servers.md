---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если вы создаете новый доверенный сервер приложений, то в смешанной среде необходимо настроить пул следующего прыжка в качестве пула в Skype для бизнеса Server 2019. В смешанной среде в раскрывающемся списке отобразятся пул устаревшего пула и пул Skype для бизнеса Server 2019. Выбор устаревшего пула не поддерживается.
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813777"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="4c9a0-105">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="4c9a0-105">Configure trusted application servers</span></span>

<span data-ttu-id="4c9a0-106">Если вы создаете новый доверенный сервер приложений, то в смешанной среде необходимо настроить пул следующего прыжка в качестве пула в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="4c9a0-107">В смешанной среде в раскрывающемся списке отобразятся пул устаревшего пула и пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="4c9a0-108">Выбор устаревшего пула не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4c9a0-109">Если вы переносите доверенный сервер приложений, необходимо также обновить версию УКМА, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="4c9a0-110">Если вы создаете новый доверенный пул приложений для Skype для бизнеса Server 2019, вы должны обновить УКМА до версии, которая входит в состав Skype для бизнеса Server 2019 или последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="4c9a0-111">Выберите Skype для бизнеса Server 2019 в качестве следующего прыжка при создании надежного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="4c9a0-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="4c9a0-112">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="4c9a0-113">На левой панели щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="4c9a0-114">Введите **полное доменное имя пула** доверенного пула приложений и укажите, будет ли он односерверным или многосерверным.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="4c9a0-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="4c9a0-116">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="4c9a0-117">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="4c9a0-118">Выберите верхний узел в **Skype для бизнеса Server**, а затем в меню **действия** выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="4c9a0-119">Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4c9a0-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

