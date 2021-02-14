---
title: 'Конфигурация собрания: создание новой или редактирование существующей'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не применяются к непъемным собраниям, созданным с помощью параметра "Выполнить сейчас" в клиенте.
ms.openlocfilehash: 87d07100e7f9411f139711de3302ce384e71cb01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824819"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="f3c0d-105">Конфигурация собрания: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="f3c0d-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="f3c0d-106">Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="f3c0d-107">Эти параметры распространяются только на запланированные собрания.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="f3c0d-108">Они не применяются к специально созданным собраниям, щелкнув параметр **"Выполнить сейчас"** в клиенте.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f3c0d-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="f3c0d-109">UI Reference</span></span>

<span data-ttu-id="f3c0d-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f3c0d-111">**Область действия** Определяет область создаемой или изменяемой конфигурации собрания: глобальную, на уровне сайта или пул.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="f3c0d-112">**Имя** Конфигурации собраний именуются по умолчанию и не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="f3c0d-113">**Вызыватели PSTN обходят "lobby"** Чтобы автоматически допустить пользователей, которые звонят на конференцию по телефонной линии телефонной сети общего звонков (PSTN), выберите этот переключатель.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="f3c0d-114">С этого момента можно отозвать звониющих по STN в "зал залов" конференции, где они находятся на удержании до тех пор, пока его не предосмотрит его.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="f3c0d-115">**Назначить в качестве presenter** Выберите категорию пользователей (помимо организатора собрания), которые автоматически назначаются в качестве участников конференции.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="f3c0d-116">Независимо от этого параметра, вы можете явным образом назначать в качестве presenters при запланированной конференции или явным образом назначать их в качестве presenter во время конференции.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="f3c0d-117">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="f3c0d-117">The options are:</span></span>

  - <span data-ttu-id="f3c0d-118">**Нет** Выберите этот параметр, если никто, кроме организатора, не будет автоматически назначен в качестве организатора.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="f3c0d-119">**Компания** Выберите этот параметр, чтобы автоматически назначать в качестве участников только участников организации.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="f3c0d-120">**Все** Выберите этот параметр, чтобы автоматически назначить кого-либо в качестве presenter.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="f3c0d-121">**Тип назначенной конференции по умолчанию** Этот параметр управляет тем, будет ли надстройка конференц-связи Outlook всегда планировать конференции с помощью назначенной организатором конференции, что означает, что запланированные конференции всегда имеют одинаковый URL-адрес join и аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="f3c0d-122">Чтобы запланированные конференции всегда использовали один и тот же URL-адрес для пользования.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="f3c0d-123">Чтобы использовать для каждой конференции разные URL-адреса пользования, с помощью этого этого окна можно использовать разные URL-адреса пользования.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="f3c0d-124">**Допуск анонимных пользователей по умолчанию** Если анонимным пользователям (то есть неавтоматическим) разрешено по умолчанию участвовать в конференциях, этот этот ящик будет разрешен.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="f3c0d-125">Если анонимным пользователям не разрешено по умолчанию посещать конференции, с помощью этого данной сети можно ото всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="f3c0d-126">**URL-адрес логотипа** Введите URL-адрес с изображением, которое будет использоваться для настраиваемого приглашения на конференцию.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="f3c0d-127">**URL-адрес справки** Введите URL-адрес веб-сайта, на котором пользователи могут получить помощь по присоединению к конференции.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="f3c0d-128">**URL-адрес юридического текста** Введите URL-адрес веб-сайта с юридическими сведениями и заявлением об отказе от ответственности для конференции.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="f3c0d-129">**Текст пользовательского footer** Введите текст, который будет использоваться в настраиваемом приглашении на конференцию.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="f3c0d-130">Дополнительные сведения о работе с конфигурациями собраний см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span> <span data-ttu-id="f3c0d-131">Дополнительные сведения о настройке конфигураций собраний для крупных собраний см. в разделе [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f3c0d-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


