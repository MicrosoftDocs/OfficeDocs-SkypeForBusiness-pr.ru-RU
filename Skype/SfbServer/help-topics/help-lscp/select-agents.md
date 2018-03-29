---
title: Выбор агентов
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Агенты — это пользователей, которые предназначены для отвечать на звонки группы ответа. Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа. Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей. Право пользователей разрешено для Скайп Business Server и корпоративной голосовой связи.
ms.openlocfilehash: ea077438b72f9e64423abf60903ceda3d96cbfa4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="select-agents"></a><span data-ttu-id="372dc-106">Выбор агентов</span><span class="sxs-lookup"><span data-stu-id="372dc-106">Select Agents</span></span>
 
<span data-ttu-id="372dc-107">Агенты — это пользователей, которые предназначены для отвечать на звонки группы ответа.</span><span class="sxs-lookup"><span data-stu-id="372dc-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="372dc-108">Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="372dc-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="372dc-109">Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей.</span><span class="sxs-lookup"><span data-stu-id="372dc-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="372dc-110">Право пользователей разрешено для Скайп Business Server и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="372dc-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span> 
  
<span data-ttu-id="372dc-111">Вы используете диалоговое окно **Выбор агентов** для выбора пользователей, добавляемых в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="372dc-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="372dc-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="372dc-112">UI Reference</span></span>

<span data-ttu-id="372dc-113">В следующем списке описываются элементы управления в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="372dc-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>
  
- <span data-ttu-id="372dc-114">**Поиск** Выполняет поиск SIP адрес или отображаемое имя для пользователя.</span><span class="sxs-lookup"><span data-stu-id="372dc-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="372dc-115">Введите полностью или частично имя или адрес.</span><span class="sxs-lookup"><span data-stu-id="372dc-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="372dc-116">Не заполняйте поле «Поиск» для отображения всех пользователей, которым разрешена для Скайп Business Server и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="372dc-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>
    
- <span data-ttu-id="372dc-117">**Максимум пользователей для отображения** Изменяет количество возвращаемых результатов, отображаемых.</span><span class="sxs-lookup"><span data-stu-id="372dc-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="372dc-118">Используйте этот счетчик для ограничения поиска, если ожидается, что много результатов.</span><span class="sxs-lookup"><span data-stu-id="372dc-118">Use this counter to limit the search if you expect many results.</span></span>
    
<span data-ttu-id="372dc-119">В следующем списке описываются поля в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="372dc-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>
  
- <span data-ttu-id="372dc-120">**Агент** Отображает имена пользователей, возвращенных в результате поиска.</span><span class="sxs-lookup"><span data-stu-id="372dc-120">**Agent** Displays the user names returned by the search.</span></span>
    
- <span data-ttu-id="372dc-121">**SIP-адрес** Отображает возвращенные поиском адреса SIP.</span><span class="sxs-lookup"><span data-stu-id="372dc-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>
    
- <span data-ttu-id="372dc-122">**Телефонная связь** Отображает значение поля **Телефония** , определенное для пользователей.</span><span class="sxs-lookup"><span data-stu-id="372dc-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>
    
- <span data-ttu-id="372dc-123">**Включено** Отображает значение поля **разрешено для Lync Server** , определенное для пользователей.</span><span class="sxs-lookup"><span data-stu-id="372dc-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>
    
<span data-ttu-id="372dc-124">Дополнительные сведения о работе с группами агентов см [Управление группами агентов](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="372dc-124">For details about working with agent groups, see [Managing Agent Groups](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>
  

