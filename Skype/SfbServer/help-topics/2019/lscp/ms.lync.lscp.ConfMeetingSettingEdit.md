---
title: Настройка собрания создание нового или изменение существующего
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента "Провести собрание" в клиенте.
ms.openlocfilehash: ce94eff347d4cbae35d78ced44873e8164abe0d5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691404"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="37404-105">Конфигурация собрания: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="37404-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="37404-p102">Параметры конфигурации собраний определяют взаимодействие с пользователем при присоединении к конференциям, запланированным пользователями. Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента **Провести собрание** в клиенте.</span><span class="sxs-lookup"><span data-stu-id="37404-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="37404-109">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="37404-109">UI Reference</span></span>

<span data-ttu-id="37404-110">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="37404-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="37404-111">**Область действия** Определяет область конфигурации собрания, которую вы создаете или изменяете: глобально, на сайте или в пуле.</span><span class="sxs-lookup"><span data-stu-id="37404-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="37404-112">**Name (имя** ) Для конфигураций собраний задано имя по умолчанию, и его нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="37404-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="37404-113">Исходящие **звонки по коммутируемой телефонной связи исходят зал** Установите этот флажок, чтобы автоматически допустить пользователей, которые подключаются к Конференции через коммутируемую телефонную сеть с телефонным подключением (PSTN).</span><span class="sxs-lookup"><span data-stu-id="37404-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="37404-114">Снимите этот флажок, чтобы перенаправлять вызывающих абонентов сети на Конференц-зал, где они находятся на удержании, пока презентатор не предоставит ему доступ к Конференции.</span><span class="sxs-lookup"><span data-stu-id="37404-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="37404-115">**Назначение в качестве выступающего** Выберите категорию пользователей (кроме организатора собрания), которые автоматически определяются как выступающие при присоединении к Конференции.</span><span class="sxs-lookup"><span data-stu-id="37404-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="37404-116">Независимо от того, где находится этот параметр, выступающие могут быть явно обозначены как выступающие при планировании Конференции, или они могут быть явным образом переданы во время конференции.</span><span class="sxs-lookup"><span data-stu-id="37404-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="37404-117">Доступны следующие варианты:</span><span class="sxs-lookup"><span data-stu-id="37404-117">The options are:</span></span>

  - <span data-ttu-id="37404-118">**None (нет** ) Выберите этот параметр, если никто, кроме организатора, не будет автоматически определен как выступающий.</span><span class="sxs-lookup"><span data-stu-id="37404-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="37404-119">**Компании** Выберите этот параметр, чтобы автоматически назначать только участников Организации в качестве выступающих.</span><span class="sxs-lookup"><span data-stu-id="37404-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="37404-120">**Все пользователи** Выберите этот параметр, чтобы автоматически назначать всех пользователей для выступающего.</span><span class="sxs-lookup"><span data-stu-id="37404-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="37404-121">**Назначенный тип конференции по умолчанию** Этот параметр определяет, будет ли надстройка конференц-связи Outlook всегда планировать конференции с помощью назначенной конференции организатора, а это значит, что у запланированных конференций всегда будет один и тот же URL-адрес и звуковая информация.</span><span class="sxs-lookup"><span data-stu-id="37404-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="37404-122">Установите этот флажок, чтобы запланированные конференции всегда использовали один и тот же URL-адрес соединения.</span><span class="sxs-lookup"><span data-stu-id="37404-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="37404-123">Снимите этот флажок, чтобы использовать другой URL-адрес присоединения для каждой конференции.</span><span class="sxs-lookup"><span data-stu-id="37404-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="37404-124">Допустить **анонимных пользователей по умолчанию** Установите этот флажок, если пользователи по умолчанию разрешены для пользователей с анонимными (то есть не прошедшими проверку подлинности) участниками.</span><span class="sxs-lookup"><span data-stu-id="37404-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="37404-125">Снимите этот флажок, если анонимные пользователи по умолчанию не разрешены для участия в конференциях.</span><span class="sxs-lookup"><span data-stu-id="37404-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="37404-126">**URL-адрес эмблемы** Введите URL-адрес изображения, которое будет использоваться для настраиваемых приглашений на конференцию.</span><span class="sxs-lookup"><span data-stu-id="37404-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="37404-127">**URL-адрес справки** Введите URL-адрес сайта, на котором пользователи смогут получить помощь для присоединения к Конференции.</span><span class="sxs-lookup"><span data-stu-id="37404-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="37404-128">**URL-адрес юридического текста** Введите URL-адрес сайта с юридическими сведениями и отказом от ответственности за конференцию.</span><span class="sxs-lookup"><span data-stu-id="37404-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="37404-129">**Настраиваемый текст нижнего колонтитула** Введите текст, который будет использоваться в настраиваемых приглашениях на конференцию.</span><span class="sxs-lookup"><span data-stu-id="37404-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="37404-p107">Дополнительные сведения о работе с конфигурациями собраний см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) документации по использованию. Дополнительные сведения о настройке конфигураций собраний для крупных собраний см. в разделе [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="37404-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


