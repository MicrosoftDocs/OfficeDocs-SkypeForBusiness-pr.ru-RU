---
title: Конфигурация версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.
ms.openlocfilehash: 69d8c15688e6afce2f1e92cebc20ad8fb6bc7464
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100655"
---
# <a name="client-version-configuration"></a><span data-ttu-id="2a88b-104">Конфигурация версий клиентов</span><span class="sxs-lookup"><span data-stu-id="2a88b-104">Client Version Configuration</span></span>

<span data-ttu-id="2a88b-p102">Кроме указания версии клиентов, поддержку которой вы хотите обеспечить в своей среде, вы можете также указать действие по умолчанию для клиентов, пока не имеющих заданной политики выбора версий. Это позволяет ограничить число используемых в среде версий клиентов, что помогает управлять затратами на поддержку нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a88b-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2a88b-107">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="2a88b-107">Tasks you can perform</span></span>

<span data-ttu-id="2a88b-108">На странице **Настройка версии клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2a88b-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="2a88b-109">Изменение конфигурации клиентской версии по умолчанию **(глобальная).**</span><span class="sxs-lookup"><span data-stu-id="2a88b-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="2a88b-110">создать настройку версии клиентов для конкретного сайта;</span><span class="sxs-lookup"><span data-stu-id="2a88b-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="2a88b-111">включить или отключить существующие настройки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a88b-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="2a88b-112">Поскольку анонимные пользователи не сопоставлены с сайтом, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="2a88b-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2a88b-113">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="2a88b-113">UI Reference</span></span>

<span data-ttu-id="2a88b-114">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="2a88b-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="2a88b-115">**Новые** Можно создать конфигурацию клиентской версии для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="2a88b-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="2a88b-116">**Изменение** Вы можете изменить параметры любой из политик клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="2a88b-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="2a88b-117">С помощью этой команды можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2a88b-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="2a88b-118">**Демонстрация сведений** Этот параметр открывает диалоговое окно, в котором можно изменить параметры конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="2a88b-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="2a88b-119">**Выберите все** Этот параметр выбирает все конфигурации клиентской версии в списке.</span><span class="sxs-lookup"><span data-stu-id="2a88b-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="2a88b-120">**Удаление** Этот параметр удаляет все выбранные конфигурации клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="2a88b-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="2a88b-121">**Обновление** Вы можете обновить список конфигурации клиентской версии, чтобы проверить состояние параметров всех конфигураций клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="2a88b-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="2a88b-122">Сведения о взаимосвязи между клиентами и версиями клиентов см. в документации по планированию. [](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)</span><span class="sxs-lookup"><span data-stu-id="2a88b-122">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="2a88b-123">Дополнительные сведения о работе с конфигурациями версий клиентов см. в разделе [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="2a88b-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>