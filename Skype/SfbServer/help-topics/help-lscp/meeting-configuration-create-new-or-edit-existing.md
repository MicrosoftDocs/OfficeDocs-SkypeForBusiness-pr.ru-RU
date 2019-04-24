---
title: Создание новой или редактирование существующей конфигурации собрания
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента "Провести собрание" в клиенте.
ms.openlocfilehash: bb2b81aa860660503522783d3ed3a3aa9ec09985
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200704"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="ecb6c-105">Конфигурация собрания: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="ecb6c-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="ecb6c-p102">Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента **Провести собрание** в клиенте.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ecb6c-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="ecb6c-109">UI Reference</span></span>

<span data-ttu-id="ecb6c-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="ecb6c-111">**Область** Определяет область создаваемой или изменяемой конфигурации собрания: глобальная, на уровне сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="ecb6c-112">**Имя** По умолчанию имя конфигурации собрания и имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="ecb6c-113">**PSTN абонентов пропускать зал ожидания** Установите этот флажок, чтобы автоматически одобрять пользователей, которые подключаются к конференции по телефонной сети (общего пользования PSTN) телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="ecb6c-114">Снимите флажок этот флажок для абонентов PSTN маршрут в конференц-зал, где они находятся на удержание до конференции выступающего предоставляет им доступа к конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="ecb6c-115">**Задать выступающего** Выберите категорию пользователей (кроме организатора собрания), которые используются для выступающих автоматически, при их присоединении к конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="ecb6c-116">Независимо от того, этот параметр докладчики могут быть явно обозначены как выступающих при планировать конференции, или они могут явно активизировать с целью выступающего во время конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="ecb6c-117">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="ecb6c-117">The options are:</span></span>

  - <span data-ttu-id="ecb6c-118">**Нет** Установите этот флажок, если никто, кроме организатора автоматически назначается в качестве выступающего.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="ecb6c-119">**Компании** Установите этот флажок, чтобы автоматически назначать в качестве выступающих только членов вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="ecb6c-120">**Всем пользователям** Установите этот флажок, чтобы автоматически назначать в качестве выступающего.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="ecb6c-121">**Тип конференции назначено по умолчанию** Данный параметр определяет, является ли надстройки конференц-связи Outlook всегда планирует конференций с помощью организатора назначенные конференции, какие означает, что запланированных конференций всегда иметь же URL-адрес соединения и аудиоданных.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="ecb6c-122">Установите этот флажок, чтобы иметь запланированного всегда использовать же URL-адрес присоединиться к конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="ecb6c-123">Снимите этот флажок, чтобы использовать разные присоединения к URL-адрес для каждой конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="ecb6c-124">**Допустить анонимных пользователей по умолчанию** Установите этот флажок, если анонимный (то есть, непроверенный) доступны пользователям в конференциях по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="ecb6c-125">Снимите этот флажок, если анонимные пользователи не допускается в конференциях по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="ecb6c-126">**URL-адрес эмблемы** Введите URL-адрес изображения, которое будет использоваться для настраиваемых приглашений на конференцию, которое.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="ecb6c-127">**URL-адрес справки** Введите URL-адрес для веб-сайта, где пользователи могут получить помощь по присоединению к конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="ecb6c-128">**URL-адрес правового документа** Введите URL-адрес для веб-сайта, содержащего юридическую информацию и заявления об отказе для конференции.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="ecb6c-129">**Пользовательский текст нижнего колонтитула** Введите текст, который будет использоваться в настраиваемых приглашений на конференцию.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="ecb6c-p107">Дополнительные сведения о работе с конфигурациями собраний см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) документации по использованию. Дополнительные сведения о настройке конфигураций собраний для крупных собраний см. в разделе [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


