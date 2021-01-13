---
title: Выбор агентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: Агенты — это пользователи, назначенные для ответа на вызовы группы ответа. Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа. Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей. Пользователи, соответствующие требованиям, могут использовать Skype для бизнеса Server и Корпоративная голосовая связь.
ms.openlocfilehash: b2eb4baa8f969c6395f51da8153c3c34f7c3684b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824669"
---
# <a name="select-agents"></a><span data-ttu-id="a238c-106">Выбор агентов</span><span class="sxs-lookup"><span data-stu-id="a238c-106">Select Agents</span></span>

<span data-ttu-id="a238c-107">Агенты — это пользователи, назначенные для ответа на вызовы группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a238c-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="a238c-108">Группе ответа должна быть назначена группа агентов, определяющая, какие агенты могут принимать звонки для данной группы ответа.</span><span class="sxs-lookup"><span data-stu-id="a238c-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="a238c-109">Один из способов создания группы агентов заключается в определении настраиваемой группы посредством выбора подходящих пользователей.</span><span class="sxs-lookup"><span data-stu-id="a238c-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="a238c-110">Пользователи, соответствующие требованиям, могут использовать Skype для бизнеса Server и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="a238c-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="a238c-111">Вы используете диалоговое окно **Выбор агентов** для выбора пользователей, добавляемых в группу агентов.</span><span class="sxs-lookup"><span data-stu-id="a238c-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a238c-112">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="a238c-112">UI Reference</span></span>

<span data-ttu-id="a238c-113">В следующем списке описываются элементы управления в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="a238c-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="a238c-114">**Поиск** Выполняет поиск SIP-адреса или отображаемой имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="a238c-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="a238c-115">Введите все или часть адреса или имени.</span><span class="sxs-lookup"><span data-stu-id="a238c-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="a238c-116">Оставьте поле поиска пустым, чтобы отобразить всех пользователей, для которых включен Skype для бизнеса Server и Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="a238c-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="a238c-117">**Максимальное число отображаемых пользователей** Изменяет количество возвращаемого результата.</span><span class="sxs-lookup"><span data-stu-id="a238c-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="a238c-118">Используйте этот счетчик, чтобы ограничить поиск, если ожидается большое количество результатов.</span><span class="sxs-lookup"><span data-stu-id="a238c-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="a238c-119">В следующем списке описываются поля в диалоговом окне **Выбор агентов**.</span><span class="sxs-lookup"><span data-stu-id="a238c-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="a238c-120">**Агент** Отображает имена пользователей, возвращенные при поиске.</span><span class="sxs-lookup"><span data-stu-id="a238c-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="a238c-121">**SIP-адрес** Отображает SIP-адреса пользователей, возвращенные поиском.</span><span class="sxs-lookup"><span data-stu-id="a238c-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="a238c-122">**Телефония** Отображает значение поля **"Телефония",** определенного для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a238c-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="a238c-123">**Включено** Отображает значение поля **"Включено для Lync Server",** определенное для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a238c-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="a238c-124">Дополнительные сведения о работе с группами агентов см. в разделе [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="a238c-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


