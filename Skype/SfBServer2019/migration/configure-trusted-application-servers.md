---
title: Настройка доверенных серверов приложений
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В смешанной среде Если вы создаете новый доверенный сервер приложений, необходимо задать пул следующих прыжков быть Скайп для пула Business Server 2019. В смешанной среде устаревшего пула и Скайп для пула Business Server 2019 отображаются в раскрывающемся списке. Выбор устаревшего пула не поддерживается.
ms.openlocfilehash: d1c79e044145a4739cf1b7bfb3992320be1e4ab3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027748"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="794c7-105">Настройка доверенных серверов приложений</span><span class="sxs-lookup"><span data-stu-id="794c7-105">Configure trusted application servers</span></span>

<span data-ttu-id="794c7-106">В смешанной среде Если вы создаете новый доверенный сервер приложений, необходимо задать пул следующих прыжков быть Скайп для пула Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="794c7-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="794c7-107">В смешанной среде устаревшего пула и Скайп для пула Business Server 2019 отображаются в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="794c7-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="794c7-108">Выбор устаревшего пула не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="794c7-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="794c7-109">При переносе сервера доверенных приложений, следует также обновить версии UCMA, вы используете.</span><span class="sxs-lookup"><span data-stu-id="794c7-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="794c7-110">При создании нового пула доверенных приложений для Скайп для Business Server 2019 UCMA должно обновить до версии, который входит в состав Скайп для Business Server 2019 или последняя доступная версия.</span><span class="sxs-lookup"><span data-stu-id="794c7-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="794c7-111">Выберите Скайп для Business Server 2019 в качестве узла следующего перехода при создании сервера доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="794c7-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="794c7-112">Откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="794c7-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="794c7-113">В левой области щелкните правой кнопкой мыши **серверы доверенных приложений** и нажмите кнопку **Создать пул доверенных приложений**.</span><span class="sxs-lookup"><span data-stu-id="794c7-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="794c7-114">Введите **Полное доменное имя пула** пула доверенных приложений и выберите будет ли это одним или несколькими серверами.</span><span class="sxs-lookup"><span data-stu-id="794c7-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="794c7-115">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="794c7-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="794c7-116">На странице **Выбор следующего прыжка** в списке выберите Скайп для пула переднего плана Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="794c7-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="794c7-117">Нажмите кнопку \*\*Готово \*\*.</span><span class="sxs-lookup"><span data-stu-id="794c7-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="794c7-118">Выберите верхний узел **Скайп для Business Server**и в меню **Действие** выберите **Опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="794c7-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="794c7-119">Убедитесь, что **Пул доверенных приложений** успешно создан и связан с соответствующим интерфейсным пулом.</span><span class="sxs-lookup"><span data-stu-id="794c7-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

