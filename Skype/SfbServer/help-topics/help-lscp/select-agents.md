---
title: Выбор агентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Агенты — это пользователи, которые предназначены для звонков групп ответов. Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа. Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей. Пользователи с подходящими учетными записью включены для Skype для бизнеса Server и Enterprise Voice.
ms.openlocfilehash: 4e80e99403b6b736722cf94ce37798a651402d03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297661"
---
# <a name="select-agents"></a><span data-ttu-id="7d148-106">Выбор агентов</span><span class="sxs-lookup"><span data-stu-id="7d148-106">Select Agents</span></span>

<span data-ttu-id="7d148-107">Агенты — это пользователи, которые предназначены для звонков групп ответов.</span><span class="sxs-lookup"><span data-stu-id="7d148-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="7d148-108">Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="7d148-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="7d148-109">Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d148-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="7d148-110">Пользователи с подходящими учетными записью включены для Skype для бизнеса Server и Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7d148-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="7d148-111">Вы используете диалоговое окно **Выбор агентов** для выбора пользователей, добавляемых в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="7d148-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7d148-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7d148-112">UI Reference</span></span>

<span data-ttu-id="7d148-113">В следующем списке описываются элементы управления в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="7d148-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="7d148-114">**Найти** Поиск адреса SIP или отображаемого имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d148-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="7d148-115">Введите адрес или имя или его часть.</span><span class="sxs-lookup"><span data-stu-id="7d148-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="7d148-116">Оставьте поле поиска пустым, чтобы отобразить всех пользователей, имеющих доступ к Skype для бизнеса Server и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7d148-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="7d148-117">**Максимальное число отображаемых пользователей** Изменяет количество отображаемых возвращаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="7d148-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="7d148-118">Используйте этот счетчик для ограничения поиска, если вы ожидаете большого количества результатов.</span><span class="sxs-lookup"><span data-stu-id="7d148-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="7d148-119">В следующем списке описываются поля в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="7d148-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="7d148-120">**Агента** Отображаются имена пользователей, возвращаемые функцией поиска.</span><span class="sxs-lookup"><span data-stu-id="7d148-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="7d148-121">**SIP Address** Отображаются адреса SIP пользователя, возвращенные функцией поиска.</span><span class="sxs-lookup"><span data-stu-id="7d148-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="7d148-122">**Телефония** Отображает значение поля телефонии \*\*\*\* , определенного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d148-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="7d148-123">**Enabled (включено** ) Отображает значение поля **Enabled для Lync Server** , определенного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d148-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="7d148-124">Дополнительные сведения о работе с группами агентов см. в разделе [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7d148-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


