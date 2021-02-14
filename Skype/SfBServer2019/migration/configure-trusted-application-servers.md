---
title: Настройка доверенных серверов приложений
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
description: В смешанной среде при создании нового доверенного сервера приложений необходимо установить пул следующего прыжка в пул Skype для бизнеса Server 2019. В смешанной среде в выпадаемом списке отображаются устаревший пул и пул Skype для бизнеса Server 2019. Предыдущую версию пула выбрать нельзя.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753949"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="0b421-105">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="0b421-105">Configure trusted application servers</span></span>

<span data-ttu-id="0b421-106">В смешанной среде при создании нового доверенного сервера приложений необходимо установить пул следующего прыжка в пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0b421-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0b421-107">В смешанной среде устаревший пул и пул Skype для бизнеса Server 2019 отображаются в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="0b421-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="0b421-108">Предыдущую версию пула выбрать нельзя.</span><span class="sxs-lookup"><span data-stu-id="0b421-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b421-109">При переносе доверенного сервера приложений также следует обновить используемую версию UCMA.</span><span class="sxs-lookup"><span data-stu-id="0b421-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="0b421-110">При создании нового пула доверенных приложений для Skype для бизнеса Server 2019 необходимо обновить UCMA до версии, включенной в Skype для бизнеса Server 2019 или последней доступной версии.</span><span class="sxs-lookup"><span data-stu-id="0b421-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="0b421-111">Выбор Skype для бизнеса Server 2019 в качестве следующего перехода при создании сервера доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="0b421-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="0b421-112">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="0b421-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0b421-113">В левой области щелкните  правой кнопкой мыши серверы доверенных приложений и выберите **"Новый пул доверенных приложений".**</span><span class="sxs-lookup"><span data-stu-id="0b421-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="0b421-114">Введите **FQDN** пула доверенных приложений и выберите, будет ли это один или несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="0b421-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="0b421-115">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0b421-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="0b421-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span><span class="sxs-lookup"><span data-stu-id="0b421-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="0b421-117">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="0b421-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="0b421-118">Выберите верхний узел **Skype для бизнеса Server** и в меню действий выберите **"Опубликовать".** </span><span class="sxs-lookup"><span data-stu-id="0b421-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="0b421-119">Убедитесь, **что пул** доверенных приложений успешно создан и связан с правильным пулом переднего входа.</span><span class="sxs-lookup"><span data-stu-id="0b421-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

