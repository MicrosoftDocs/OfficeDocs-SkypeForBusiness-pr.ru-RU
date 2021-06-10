---
title: Общедоступная предварительная версия в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Ознакомьтесь с общедоступной предварительной версией в Microsoft Teams. Опробуйте новые возможности и поделитесь отзывами.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0719e68dcbf1c73c15ee58e8c7d6be08f359aa5
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863260"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="4df5b-104">Общедоступная предварительная версия Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4df5b-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="4df5b-p102">Функции, включенные в предварительную версию, могут быть неполными. Они также могут быть изменены перед общедоступным выпуском. Они предназначены только для оценки и изучения. Не поддерживается в облаке сообщества Office 365 для государственных организаций (GCC).</span><span class="sxs-lookup"><span data-stu-id="4df5b-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="4df5b-p103">Общедоступная предварительная версия Microsoft Teams обеспечивает ранний доступ к невыпущенным функциям в Teams. Предварительные версии позволяют вам изучать и тестировать будущие функции. Мы также будем рады вашим отзывам о любых функциях из общедоступных предварительных версий. Общедоступная предварительная версия включается для каждого пользователя Teams отдельно, поэтому вам не нужно беспокоиться о влиянии на всю вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="4df5b-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="4df5b-112">Список возможностей, присутствующих в общедоступной предварительной версии Teams, см. в [заметках о выпуске Актуального канала Office (предварительная версия)](/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="4df5b-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="4df5b-113">Настройка политики обновления</span><span class="sxs-lookup"><span data-stu-id="4df5b-113">Set the Update policy</span></span>

<span data-ttu-id="4df5b-p104">Общедоступная предварительная версия включается для каждого пользователя, а параметр включения общедоступной предварительной версии управляется политикой администрирования. Политики обновления используются для управления пользователями предварительных версий Teams и Office, которым будут показаны предварительные функции в приложении Teams. Вы можете использовать глобальную (по умолчанию для всей организации) политику и настроить ее или создать одну или несколько настраиваемых политик для своих пользователей. Политику следует назначать конкретным пользователям, так как она не переопределяет глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="4df5b-p104">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy. Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app. You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users. The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="4df5b-118">Войдите в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4df5b-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="4df5b-119">Выберите **Команды**>**Политики обновления**.</span><span class="sxs-lookup"><span data-stu-id="4df5b-119">Select **Teams**>**Update policies**.</span></span>

   ![Выбор параметра "Политики обновления"](media/updatePolicies.png)

3. <span data-ttu-id="4df5b-121">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4df5b-121">Select **Add**.</span></span>
4. <span data-ttu-id="4df5b-122">Назовите политику обновления, добавьте описание и включите параметр **Показать функции предварительного просмотра**.</span><span class="sxs-lookup"><span data-stu-id="4df5b-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="4df5b-123">Вы также можете настроить политику с помощью командлета `CsTeamsUpdateManagementPolicy` в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4df5b-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="4df5b-124">Включение общедоступной предварительной версии</span><span class="sxs-lookup"><span data-stu-id="4df5b-124">Enable public preview</span></span>

<span data-ttu-id="4df5b-125">Чтобы включить общедоступную предварительную версию в классическом или веб-клиенте, вам требуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4df5b-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="4df5b-126">Выберите три точки слева от профиля, чтобы отобразилось меню Teams.</span><span class="sxs-lookup"><span data-stu-id="4df5b-126">Select the three dots to the left of your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="4df5b-127">Выберите **О программе** > **Общедоступная предварительная версия**.</span><span class="sxs-lookup"><span data-stu-id="4df5b-127">Select **About** > **Public preview**.</span></span>
3. <span data-ttu-id="4df5b-128">Выберите **Переключиться на общедоступную предварительную версию**.</span><span class="sxs-lookup"><span data-stu-id="4df5b-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4df5b-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4df5b-129">Related topics</span></span>

[<span data-ttu-id="4df5b-130">Предварительная общедоступная версия для разработчиков</span><span class="sxs-lookup"><span data-stu-id="4df5b-130">Public developer preview</span></span>](/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
