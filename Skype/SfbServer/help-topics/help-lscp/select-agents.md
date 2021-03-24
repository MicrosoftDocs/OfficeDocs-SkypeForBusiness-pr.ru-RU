---
title: Выбор агентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
description: Агенты — это пользователи, назначенные для ответа на вызовы группы ответов. Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа. Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей. Соответствующие пользователи включены для Skype для бизнес-сервера и Корпоративная голосовая связь.
ms.openlocfilehash: c245ea9816d60fc8448eeeb00bdfc8351e345784
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108005"
---
# <a name="select-agents"></a><span data-ttu-id="0cf28-106">Выбор агентов</span><span class="sxs-lookup"><span data-stu-id="0cf28-106">Select Agents</span></span>

<span data-ttu-id="0cf28-107">Агенты — это пользователи, назначенные для ответа на вызовы группы ответов.</span><span class="sxs-lookup"><span data-stu-id="0cf28-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="0cf28-108">Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0cf28-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="0cf28-109">Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей.</span><span class="sxs-lookup"><span data-stu-id="0cf28-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="0cf28-110">Соответствующие пользователи включены для Skype для бизнес-сервера и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="0cf28-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="0cf28-111">Вы используете диалоговое окно **Выбор агентов** для выбора пользователей, добавляемых в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="0cf28-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0cf28-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="0cf28-112">UI Reference</span></span>

<span data-ttu-id="0cf28-113">В следующем списке описываются элементы управления в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="0cf28-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="0cf28-114">**Поиск** Поиск адреса SIP или отображения имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="0cf28-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="0cf28-115">Введите все или часть адреса или имени.</span><span class="sxs-lookup"><span data-stu-id="0cf28-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="0cf28-116">Оставьте поле поиска пустым, чтобы отобразить всех пользователей, включенных для Skype для бизнес-сервера и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="0cf28-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="0cf28-117">**Максимальное число отображаемых пользователей** Изменяет количество отображаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="0cf28-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="0cf28-118">Используйте этот счетчик, чтобы ограничить поиск, если ожидается много результатов.</span><span class="sxs-lookup"><span data-stu-id="0cf28-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="0cf28-119">В следующем списке описываются поля в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="0cf28-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="0cf28-120">**Агент** Отображает имена пользователей, возвращенные поиском.</span><span class="sxs-lookup"><span data-stu-id="0cf28-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="0cf28-121">**SIP-адрес** Отображает пользовательские SIP-адреса, возвращенные поиском.</span><span class="sxs-lookup"><span data-stu-id="0cf28-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="0cf28-122">**Телефония** Отображает значение поля **телефонии,** определенного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="0cf28-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="0cf28-123">**Включено** Отображает значение поля **Enabled for Lync Server,** определенного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="0cf28-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="0cf28-124">Дополнительные сведения о работе с группами агентов см. в разделе [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="0cf28-124">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>