---
title: Конфигурация версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Кроме возможности задания версии клиентов, которые вы хотите поддержки в среде, можно также указать действие по умолчанию для клиентов, которые еще не определена политика версии. Это позволяет ограничить, какие версии клиента, используемых в вашей среде, которые позволяют контролировать расходы, связанные с поддержкой нескольких версий клиента.
ms.openlocfilehash: d35872df068c651f4f9540e806e81cc57bd61e0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891931"
---
# <a name="client-version-configuration"></a><span data-ttu-id="6270d-104">Конфигурация версий клиентов</span><span class="sxs-lookup"><span data-stu-id="6270d-104">Client Version Configuration</span></span>

<span data-ttu-id="6270d-105">Кроме возможности задания версии клиентов, которые вы хотите поддержки в среде, можно также указать действие по умолчанию для клиентов, которые еще не определена политика версии.</span><span class="sxs-lookup"><span data-stu-id="6270d-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="6270d-106">Это позволяет ограничить, какие версии клиента, используемых в вашей среде, которые позволяют контролировать расходы, связанные с поддержкой нескольких версий клиента.</span><span class="sxs-lookup"><span data-stu-id="6270d-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6270d-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="6270d-107">Tasks you can perform</span></span>

<span data-ttu-id="6270d-108">На странице **Конфигурация версии клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="6270d-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="6270d-109">Изменение конфигурации версий клиентов по умолчанию ( **Глобальная**).</span><span class="sxs-lookup"><span data-stu-id="6270d-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="6270d-110">Создайте настройку версии клиентов для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="6270d-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="6270d-111">Включить или отключить существующие настройки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="6270d-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="6270d-112">Поскольку анонимные пользователи не сопоставлены с сайтом, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="6270d-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6270d-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="6270d-113">UI Reference</span></span>

<span data-ttu-id="6270d-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="6270d-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6270d-115">**Новые** Можно создать настройку версии клиентов для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="6270d-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="6270d-116">**Изменение** Можно изменить параметры любого из политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="6270d-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="6270d-117">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="6270d-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="6270d-118">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для конфигурации версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="6270d-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="6270d-119">**Выделить все** Этот параметр выбирает все конфигурации версии клиента в списке.</span><span class="sxs-lookup"><span data-stu-id="6270d-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="6270d-120">**Удаление** Этот параметр удаляет все настройки версий выбранных клиентов.</span><span class="sxs-lookup"><span data-stu-id="6270d-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="6270d-121">**Обновление** Можно обновить список конфигурации версии клиента, чтобы проверить состояние параметров всех конфигураций версии клиента.</span><span class="sxs-lookup"><span data-stu-id="6270d-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="6270d-122">Для получения дополнительных сведений о взаимодействии между клиентами и их версий в документации по планированию показано [Взаимодействие с клиентом](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6270d-122">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="6270d-123">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="6270d-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

