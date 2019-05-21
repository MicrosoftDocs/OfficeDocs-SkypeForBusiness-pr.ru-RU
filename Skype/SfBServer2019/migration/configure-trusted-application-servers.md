---
title: Настройка доверенных серверов приложений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если вы создаете новый доверенный сервер приложений, то в смешанной среде необходимо настроить пул следующего прыжка в качестве пула в Skype для бизнеса Server 2019. В смешанной среде в раскрывающемся списке отобразятся пул устаревшего пула и пул Skype для бизнеса Server 2019. Выбор устаревшего пула не поддерживается.
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289601"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="56275-105">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="56275-105">Configure trusted application servers</span></span>

<span data-ttu-id="56275-106">Если вы создаете новый доверенный сервер приложений, то в смешанной среде необходимо настроить пул следующего прыжка в качестве пула в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56275-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="56275-107">В смешанной среде в раскрывающемся списке отобразятся пул устаревшего пула и пул Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56275-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="56275-108">Выбор устаревшего пула не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="56275-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="56275-109">Если вы переносите доверенный сервер приложений, необходимо также обновить версию УКМА, которую вы используете.</span><span class="sxs-lookup"><span data-stu-id="56275-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="56275-110">Если вы создаете новый доверенный пул приложений для Skype для бизнеса Server 2019, вы должны обновить УКМА до версии, которая входит в состав Skype для бизнеса Server 2019 или последнюю доступную версию.</span><span class="sxs-lookup"><span data-stu-id="56275-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="56275-111">Выберите Skype для бизнеса Server 2019 в качестве следующего прыжка при создании надежного сервера приложений</span><span class="sxs-lookup"><span data-stu-id="56275-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="56275-112">Открытие построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="56275-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="56275-113">На левой панели щелкните правой кнопкой мыши **Доверенные серверы приложений** и выберите команду **создать доверенный пул приложений**.</span><span class="sxs-lookup"><span data-stu-id="56275-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="56275-114">Введите **полное доменное имя пула** доверенного пула приложений и укажите, будет ли он односерверным или многосерверным.</span><span class="sxs-lookup"><span data-stu-id="56275-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="56275-115">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="56275-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="56275-116">На странице **Выбор следующего прыжка** в списке выберите пул переднего плана Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56275-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="56275-117">Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="56275-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="56275-118">Выберите верхний узел в **Skype для бизнеса Server**, а затем в меню **действия** выберите команду **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="56275-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="56275-119">Убедитесь, что **доверенный пул приложений** успешно создан и связан с правильным пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="56275-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

