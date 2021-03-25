---
title: Конфигурация собраний Создание новых или изменение существующих
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
description: Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не применяются к ad-hoc собраниям, созданным путем нажатия параметра Meet Now в клиенте.
ms.openlocfilehash: 3d37b1894531a62f605f083cbe1e2f36953f2ff2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121133"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="08763-105">Конфигурация собрания: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="08763-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="08763-106">Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями.</span><span class="sxs-lookup"><span data-stu-id="08763-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="08763-107">Эти параметры распространяются только на запланированные собрания.</span><span class="sxs-lookup"><span data-stu-id="08763-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="08763-108">Они не применяются к ad-hoc собраниям, созданным путем нажатия **параметра Meet Now** в клиенте.</span><span class="sxs-lookup"><span data-stu-id="08763-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="08763-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="08763-109">UI Reference</span></span>

<span data-ttu-id="08763-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="08763-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="08763-111">**Область** Определяет область конфигурации собраний, которую вы создаете или модифицируют: глобальную, сайт или пул.</span><span class="sxs-lookup"><span data-stu-id="08763-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="08763-112">**Имя** Конфигурации собраний называются по умолчанию, и имя не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="08763-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="08763-113">**Обход вестибюля для звонителей PSTN** Выберите этот контрольный ящик, чтобы автоматически впустить пользователей, которые звонят на конференцию по телефонной линии с общедоступным переключение телефонной сети (PSTN).</span><span class="sxs-lookup"><span data-stu-id="08763-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="08763-114">Очистить этот контрольный окне для маршрутирования звонит PSTN в лобби конференции, где они находятся на удержании до тех пор, пока представителю конференции не предоставляется доступ к конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="08763-115">**Назначать в качестве презентера** Выберите категорию пользователей (помимо организатора собраний), которые автоматически назначаются в качестве участников конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="08763-116">Независимо от этого параметра, передатели могут быть явно назначены в качестве презентеров, когда конференция запланирована, или они могут быть явно повышены до презентатора во время конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="08763-117">Доступны следующие варианты.</span><span class="sxs-lookup"><span data-stu-id="08763-117">The options are:</span></span>

  - <span data-ttu-id="08763-118">**None** Выберите этот параметр, если никто, кроме организатора, не будет автоматически назначен в качестве презентщика.</span><span class="sxs-lookup"><span data-stu-id="08763-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="08763-119">**Компания** Выберите этот параметр, чтобы автоматически назначать в качестве презентов только членов организации.</span><span class="sxs-lookup"><span data-stu-id="08763-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="08763-120">**Все** Выберите этот параметр, чтобы автоматически назначить кого-либо в качестве презентовщика.</span><span class="sxs-lookup"><span data-stu-id="08763-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="08763-121">**Назначен тип конференции по умолчанию** Этот параметр контролирует, всегда ли Addin конференций Outlook Conferencing запланировать конференции с помощью назначенной организатором конференции, что означает, что запланированные конференции всегда имеют один и тот же URL-адрес и аудиозаписи.</span><span class="sxs-lookup"><span data-stu-id="08763-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="08763-122">Выберите этот контрольный ящик, чтобы запланированные конференции всегда использовали один и тот же URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="08763-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="08763-123">Очистить этот контрольный ящик, чтобы использовать другой URL-адрес для каждой конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="08763-124">**Прием анонимных пользователей по умолчанию** Выберите этот контрольный ящик, если анонимным (то есть неавентическим) пользователям разрешено посещать конференции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08763-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="08763-125">Очистить этот контрольный ящик, если анонимным пользователям не разрешено посещать конференции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08763-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="08763-126">**URL-адрес логотипа** Введите URL-адрес с изображением, используемым для настраиваемого приглашения на конференцию.</span><span class="sxs-lookup"><span data-stu-id="08763-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="08763-127">**URL-адрес справки** Введите URL-адрес веб-сайта, на котором пользователи могут получить помощь для присоединения к конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="08763-128">**URL-адрес юридического текста** Введите URL-адрес веб-сайта с юридическими сведениями и отказами для конференции.</span><span class="sxs-lookup"><span data-stu-id="08763-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="08763-129">**Текст настраиваемой подножки** Введите текст, который будет использоваться в настраиваемом приглашении на конференцию.</span><span class="sxs-lookup"><span data-stu-id="08763-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="08763-130">Дополнительные сведения о работе с конфигурациями собраний см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="08763-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span> <span data-ttu-id="08763-131">Дополнительные сведения о настройке конфигураций собраний для крупных собраний см. в разделе [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="08763-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in the Planning documentation.</span></span>