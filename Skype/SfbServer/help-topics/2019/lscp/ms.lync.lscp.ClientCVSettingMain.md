---
title: Конфигурация версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Кроме того, чтобы указать версию клиентов, которые вы хотите поддерживать в вашей среде, вы также можете задать действие по умолчанию для клиентов, у которых еще не определена политика управления версиями. Это позволяет ограничить использование клиентских версий в среде, что поможет вам управлять затратами, связанными с поддержкой нескольких клиентских версий.
ms.openlocfilehash: e5675a2b3cab2309a78c2d8dc88041beee8cc619
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794568"
---
# <a name="client-version-configuration"></a><span data-ttu-id="7191f-104">Конфигурация версий клиентов</span><span class="sxs-lookup"><span data-stu-id="7191f-104">Client Version Configuration</span></span>

<span data-ttu-id="7191f-105">Кроме того, чтобы указать версию клиентов, которые вы хотите поддерживать в вашей среде, вы также можете задать действие по умолчанию для клиентов, у которых еще не определена политика управления версиями.</span><span class="sxs-lookup"><span data-stu-id="7191f-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="7191f-106">Это позволяет ограничить использование клиентских версий в среде, что поможет вам управлять затратами, связанными с поддержкой нескольких клиентских версий.</span><span class="sxs-lookup"><span data-stu-id="7191f-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7191f-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="7191f-107">Tasks you can perform</span></span>

<span data-ttu-id="7191f-108">На странице **Configuration Version (версия клиента** ) можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7191f-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="7191f-109">Измените конфигурацию версии клиента по умолчанию ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="7191f-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="7191f-110">Создание конфигурации клиентской версии для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="7191f-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="7191f-111">Включение и отключение существующих конфигураций версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="7191f-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="7191f-112">Поскольку анонимные пользователи не связаны с сайтом, политики глобального уровня влияют на анонимные пользователи.</span><span class="sxs-lookup"><span data-stu-id="7191f-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7191f-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7191f-113">UI Reference</span></span>

<span data-ttu-id="7191f-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7191f-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="7191f-115">**Новые** Вы можете создать конфигурацию версии клиента для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="7191f-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="7191f-116">**Изменить** Вы можете изменить параметры любой из политик версии клиента.</span><span class="sxs-lookup"><span data-stu-id="7191f-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="7191f-117">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="7191f-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="7191f-118">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="7191f-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="7191f-119">**Выделить все** Этот параметр выбирает все конфигурации клиентской версии в списке.</span><span class="sxs-lookup"><span data-stu-id="7191f-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="7191f-120">**Delete (удалить** ) Этот параметр удаляет все выбранные конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="7191f-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="7191f-121">**Обновить** Вы можете обновить список конфигурации версии клиента, чтобы проверить состояние параметров всех конфигураций версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="7191f-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="7191f-122">Сведения о взаимодействии между клиентами и клиентской версией можно найти в разделе [взаимодействие с клиентами](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7191f-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7191f-123">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7191f-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

