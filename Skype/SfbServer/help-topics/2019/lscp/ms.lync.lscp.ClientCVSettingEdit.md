---
title: Конфигурация версии клиента создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации используются для включения и отключения управления версиями клиентов. Конфигурация глобальной клиентской версии устанавливается вместе с приложением Skype для бизнеса Server и используется для включения или отключения управления версиями для всего развертывания сервера. Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов. Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.
ms.openlocfilehash: 54a7929f91e4e944cbe431ae7a0193c50a12cfbd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300489"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="becbb-106">Конфигурация версии клиента: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="becbb-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="becbb-107">Параметры конфигурации используются для включения и отключения управления версиями клиентов.</span><span class="sxs-lookup"><span data-stu-id="becbb-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="becbb-108">Конфигурация глобальной клиентской версии устанавливается вместе с приложением Skype для бизнеса Server и используется для включения или отключения управления версиями для всего развертывания сервера.</span><span class="sxs-lookup"><span data-stu-id="becbb-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="becbb-109">Когда включена глобальная конфигурация, при попытке пользователя войти в систему применяются все заданные политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="becbb-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="becbb-110">Вы можете отключить глобальную конфигурацию версий клиентов, если не хотите применять какое-либо управление версиями.</span><span class="sxs-lookup"><span data-stu-id="becbb-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="becbb-p103">Вы также можете создать конфигурации версий клиентов для индивидуальных сайтов, что позволяет включать и отключать управление версиями клиентов для отдельного сайта. Конфигурации для индивидуальных сайтов имеют приоритет над глобальной конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="becbb-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="becbb-113">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="becbb-113">Tasks you can perform</span></span>

<span data-ttu-id="becbb-114">Вы можете выполнить следующие задачи на странице **Новая настройка версии клиента** или **Изменить настройку версии клиента**:</span><span class="sxs-lookup"><span data-stu-id="becbb-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="becbb-115">Добавление или изменение имени конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="becbb-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="becbb-116">Включение или отключение управления версиями клиентов на глобальном уровне или для отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="becbb-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="becbb-117">Добавление или изменение действия по умолчанию для конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="becbb-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="becbb-118">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="becbb-118">UI Reference</span></span>

<span data-ttu-id="becbb-119">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="becbb-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="becbb-120">**Область действия** Определяет область (глобальную или веб-сайт) конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="becbb-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="becbb-121">**Name (имя** ) Вы можете добавить или изменить название конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="becbb-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="becbb-122">**Включение управления версиями** Вы можете включить или отключить управление версией клиента на глобальном уровне или на сайте, в зависимости от области конфигурации.</span><span class="sxs-lookup"><span data-stu-id="becbb-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="becbb-123">**Действие по умолчанию** Вы можете выбрать действие по умолчанию, которое будет применяться, когда пользователь попытается войти в систему с помощью клиентского приложения, для которого нет особой политики версии клиента.</span><span class="sxs-lookup"><span data-stu-id="becbb-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="becbb-124">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="becbb-124">You have the following options:</span></span>

  - <span data-ttu-id="becbb-125">**Разрешение** Позволяет клиенту входить в систему, если клиентская версия не совпадает ни с одним фильтром в списке политик версии клиента.</span><span class="sxs-lookup"><span data-stu-id="becbb-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="becbb-126">**Блокировать** Запрещает клиенту входить в систему, если клиентская версия не совпадает ни с одним фильтром в списке политик версии клиента.</span><span class="sxs-lookup"><span data-stu-id="becbb-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="becbb-127">**Блокировка с URL-адресом** Запрещает клиенту входить в систему, если клиентская версия не совпадает ни с одним фильтром в списке политики версии клиента, и содержит сообщение об ошибке с URL-адресом, по которому можно скачать более новый клиент.</span><span class="sxs-lookup"><span data-stu-id="becbb-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="becbb-128">**Разрешить с URL-адресом** Позволяет клиенту входить в систему, если клиентская версия не соответствует ни одному фильтру в списке политики версии клиента, и содержит сообщение об ошибке с URL-адресом, по которому можно скачать более новый клиент.</span><span class="sxs-lookup"><span data-stu-id="becbb-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="becbb-129">**URL-адрес** Если вы выбрали параметр **блокировать с** URL-адресом или **Разрешить с URL-** адресом, вы можете указать URL-адрес скачивания клиента, который нужно включить в сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="becbb-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="becbb-130">Сведения о взаимодействии между клиентами и клиентской версией можно найти в разделе [взаимодействие с клиентами](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="becbb-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="becbb-131">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="becbb-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

