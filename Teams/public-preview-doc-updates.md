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
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043963"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="a6281-104">Общедоступная предварительная версия Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a6281-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="a6281-p102">Функции, включенные в предварительную версию, могут быть неполными. Они также могут быть изменены перед общедоступным выпуском. Они предназначены только для оценки и изучения.</span><span class="sxs-lookup"><span data-stu-id="a6281-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="a6281-p103">Общедоступная предварительная версия Microsoft Teams обеспечивает ранний доступ к невыпущенным функциям в Teams. Предварительные версии позволяют вам изучать и тестировать будущие функции. Мы также будем рады вашим отзывам о любых функциях из общедоступных предварительных версий. Общедоступная предварительная версия включается для каждого пользователя Teams отдельно, поэтому вам не нужно беспокоиться о влиянии на всю вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="a6281-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="a6281-111">Список возможностей, присутствующих в общедоступной предварительной версии Teams, см. в [заметках о выпуске Актуального канала Office (предварительная версия)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span><span class="sxs-lookup"><span data-stu-id="a6281-111">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="a6281-112">Настройка политики обновления</span><span class="sxs-lookup"><span data-stu-id="a6281-112">Set the Update policy</span></span>

<span data-ttu-id="a6281-113">Общедоступная предварительная версия включается для каждого пользователя отдельно, а параметр включения общедоступной предварительной версии управляется политикой администрирования.</span><span class="sxs-lookup"><span data-stu-id="a6281-113">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="a6281-114">Политики обновления используются для управления пользователями предварительных версий Teams и Office, которым будут демонстрироваться предварительные функции в приложении Teams.</span><span class="sxs-lookup"><span data-stu-id="a6281-114">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="a6281-115">Вы можете использовать глобальную (по умолчанию для всей организации) политику и настроить ее или создать одну или несколько настраиваемых политик для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="a6281-115">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="a6281-116">Политику требуется назначать конкретным пользователям, так как она не переопределяет глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="a6281-116">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="a6281-117">Войдите в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="a6281-117">Sign in to the admin center.</span></span>
2. <span data-ttu-id="a6281-118">Выберите **Команды**>**Политики обновления**.</span><span class="sxs-lookup"><span data-stu-id="a6281-118">Select **Teams**>**Update policies**.</span></span>

   ![Выбор параметра "Политики обновления"](media/updatePolicies.png)

3. <span data-ttu-id="a6281-120">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="a6281-120">Select **Add**.</span></span>
4. <span data-ttu-id="a6281-121">Назовите политику обновления, добавьте описание и включите параметр **Показать функции предварительного просмотра**.</span><span class="sxs-lookup"><span data-stu-id="a6281-121">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="a6281-122">Вы также можете настроить политику с помощью командлета `CsTeamsUpdateManagementPolicy` в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a6281-122">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="a6281-123">Включение общедоступной предварительной версии</span><span class="sxs-lookup"><span data-stu-id="a6281-123">Enable public preview</span></span>

<span data-ttu-id="a6281-124">Чтобы включить общедоступную предварительную версию в классическом или веб-клиенте, вам требуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a6281-124">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="a6281-125">Выберите свой профиль, чтобы открыть меню Teams.</span><span class="sxs-lookup"><span data-stu-id="a6281-125">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="a6281-126">Выберите **О приложении** → **Общедоступная предварительная версия**.</span><span class="sxs-lookup"><span data-stu-id="a6281-126">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="a6281-127">Выберите **Переключиться на общедоступную предварительную версию**.</span><span class="sxs-lookup"><span data-stu-id="a6281-127">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a6281-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a6281-128">Related topics</span></span>

[<span data-ttu-id="a6281-129">Предварительная общедоступная версия для разработчиков</span><span class="sxs-lookup"><span data-stu-id="a6281-129">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

