---
title: Политики хранения в Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Используйте политики хранения для Microsoft Teams для хранения сообщений, которые должны соответствовать внутренним политикам, отраслевым нормам или законодательным требованиям, а также для удаления сообщений, которые считаются ответственности или не имеют ценности для бизнеса.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786831"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="4ce57-103">Политики хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ce57-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="4ce57-104">Политики хранения и метки хранения из Microsoft 365 помогут вам более эффективно управлять информацией в организации.</span><span class="sxs-lookup"><span data-stu-id="4ce57-104">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="4ce57-105">Вы можете настроить параметры хранения для хранения данных, которые должны соответствовать внутренним политикам, отраслевым требованиям или законодательным требованиям организации.</span><span class="sxs-lookup"><span data-stu-id="4ce57-105">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal needs.</span></span> <span data-ttu-id="4ce57-106">Вы также можете настроить параметры хранения для удаления данных, которые считаются ответственности, которые больше не требуются для сохранения или которые не имеют ценности для юридических или деловых данных.</span><span class="sxs-lookup"><span data-stu-id="4ce57-106">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="4ce57-107">Teams поддерживает политики хранения для сообщений чата и каналов, чтобы как администратор вы как администратор могли заранее решить, сохранять или удалять эти данные, удалять их или хранить в течение определенного периода времени, а затем удалять.</span><span class="sxs-lookup"><span data-stu-id="4ce57-107">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="4ce57-108">Вы можете применить политику хранения Teams ко всей организации или отдельным пользователям и командам.</span><span class="sxs-lookup"><span data-stu-id="4ce57-108">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="4ce57-109">Метки хранения не поддерживаются в Teams.</span><span class="sxs-lookup"><span data-stu-id="4ce57-109">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="4ce57-110">Чтобы узнать больше о хранении и применении параметров хранения с помощью политик хранения или меток хранения для других рабочих нагрузок в Microsoft 365, см. статью о политиках хранения и метах [хранения.](https://docs.microsoft.com/microsoft-365/compliance/retention)</span><span class="sxs-lookup"><span data-stu-id="4ce57-110">To learn more about retention, and how you can apply retention settings by using retention policies or retention labels for other workloads in Microsoft 365, see [Learn about retention policies and retention labels](https://docs.microsoft.com/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="4ce57-111">Минимальное лицензионное требование для политик хранения для Teams — Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4ce57-111">The minimum licensing requirement for retention policies for Teams is Microsoft 365 E3.</span></span> <span data-ttu-id="4ce57-112">Дополнительные информацию о лицензировании см. в описании [службы Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="4ce57-112">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-work"></a><span data-ttu-id="4ce57-113">Как работают политики хранения Teams</span><span class="sxs-lookup"><span data-stu-id="4ce57-113">How Teams retention policies work</span></span>

<span data-ttu-id="4ce57-114">Сообщения чата Teams хранятся в скрытой папке в почтовом ящике каждого пользователя, включенного в чат, а сообщения каналов Teams — в похожей скрытой папке почтового ящика группы для команды.</span><span class="sxs-lookup"><span data-stu-id="4ce57-114">Teams chat messages are stored in a hidden folder in the mailbox of each user included in the chat, and Teams channel messages are stored in a similar hidden folder in the group mailbox for the team.</span></span> <span data-ttu-id="4ce57-115">Чтобы сохранить сообщения, на которые налагается политика хранения, их копия автоматически сохраняется в скрытой папке **SubstrateHolds** как вложенной папке в папке Exchange **Recoverable Items.**</span><span class="sxs-lookup"><span data-stu-id="4ce57-115">To retain messages that are subject to a retention policy, a copy of the content is automatically kept in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.</span></span> <span data-ttu-id="4ce57-116">Пока эти сообщения не будут удалены окончательно из папки SubstrateHolds, они останутся доступны для поиска с помощью средств eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4ce57-116">Until these messages are permanently deleted from the SubstrateHolds folder, they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="4ce57-117">Подробные сведения о том, какие возможности включены и исключены для политик хранения Teams, а также о том, как они работают в зависимости от конфигурации политики, см. в сведениях о хранении для [Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)</span><span class="sxs-lookup"><span data-stu-id="4ce57-117">For detailed information about what's included and excluded for Teams retention policies, and how these policies work depending on your policy configuration, see [Learn about retention for Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="4ce57-118">На этой странице объясняется, почему иногда могут возникнуть задержки при удалении сообщений политиками хранения.</span><span class="sxs-lookup"><span data-stu-id="4ce57-118">That page explains why you might sometimes see delays when retention policies delete messages.</span></span> <span data-ttu-id="4ce57-119">Например, сообщения могут быть видны в течение 7 дней после истечения срока действия, настроенного в политике хранения.</span><span class="sxs-lookup"><span data-stu-id="4ce57-119">For example, messages can be visible up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="4ce57-120">Если вы настроили несколько политик хранения Teams с различными настройками хранения, принципы хранения устраняют любые конфликты.</span><span class="sxs-lookup"><span data-stu-id="4ce57-120">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="4ce57-121">Например:</span><span class="sxs-lookup"><span data-stu-id="4ce57-121">For example:</span></span>
- <span data-ttu-id="4ce57-122">Если есть конфликт между сохранением и удалением одного и того же содержимого, содержимое всегда сохраняется.</span><span class="sxs-lookup"><span data-stu-id="4ce57-122">If there is a conflict between retaining or deleting the same content, the content is always retained.</span></span>
- <span data-ttu-id="4ce57-123">Если есть конфликт между сроком хранения того же содержимого, оно сохраняется в течение самого длительного из них.</span><span class="sxs-lookup"><span data-stu-id="4ce57-123">If there is a conflict in how long to retain the same content, it is retained for the longest retention period.</span></span>

<span data-ttu-id="4ce57-124">Эти два принципы устранения большинства конфликтов, которые могут возникнуть, если у вас есть несколько политик хранения для Teams, но для получения дополнительных сведений см. принципы хранения или что имеет [приоритет?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span><span class="sxs-lookup"><span data-stu-id="4ce57-124">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="4ce57-125">Когда применять политики хранения для Teams</span><span class="sxs-lookup"><span data-stu-id="4ce57-125">When to use retention policies for Teams</span></span>

<span data-ttu-id="4ce57-126">Во многих случаях организации считают данные приватных чатов большей ответственностью, чем сообщения каналов, беседы в которых обычно связаны с проектами.</span><span class="sxs-lookup"><span data-stu-id="4ce57-126">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="4ce57-127">Вы можете настроить отдельные политики хранения для приватных чатов (индивидуальных или групповых чатов) и сообщений каналов.</span><span class="sxs-lookup"><span data-stu-id="4ce57-127">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="4ce57-128">Кроме того, вы можете настроить уникальные политики, применяемые к определенным пользователям или командам в организации.</span><span class="sxs-lookup"><span data-stu-id="4ce57-128">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="4ce57-129">В случае чатов Teams можно выбрать пользователей, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="4ce57-129">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="4ce57-130">В случае сообщений каналов Teams можно выбрать команды, к которым применяется политика.</span><span class="sxs-lookup"><span data-stu-id="4ce57-130">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="4ce57-131">Например, в случае сообщений каналов к определенным командам в организации можно применять политику удаления со сроком один год, а для остальных команд — политику удаления со сроком три года.</span><span class="sxs-lookup"><span data-stu-id="4ce57-131">For example, for channel messages, you can apply a one-year deletion policy to specific teams in your organization and apply a three-year deletion policy to all other teams.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="4ce57-132">Создание политик хранения для Teams и управление ими</span><span class="sxs-lookup"><span data-stu-id="4ce57-132">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="4ce57-133">Чтобы создать политику хранения для чатов и сообщений каналов Teams, воспользуйтесь инструкциями из политики хранения [для местоположений Teams.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)</span><span class="sxs-lookup"><span data-stu-id="4ce57-133">To create a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="4ce57-134">На этой странице есть дополнительные сведения о создании политик хранения для других рабочих нагрузок в Microsoft 365 и управлении их политиками.</span><span class="sxs-lookup"><span data-stu-id="4ce57-134">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="4ce57-135">Например, может потребоваться создать политику хранения для групп Microsoft 365, чтобы хранить и удалять файлы, которые хранятся в Teams и хранятся в OneDrive или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ce57-135">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="4ce57-136">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="4ce57-136">End user experience</span></span>

<span data-ttu-id="4ce57-137">Для приватных (1:1) или групповых чатов конечные пользователи будут видеть, что чаты старше, чем настройка политики хранения, удаляются, а над незавершными сообщениями отображается control message с сообщением "Мы удалили старые сообщения в связи с политикой хранения вашей организации".</span><span class="sxs-lookup"><span data-stu-id="4ce57-137">For private chats (1:1 chats) or group chats, the end users will see that chats older than the retention policy configuration are deleted and a control message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="Пользователь, сообщая в Teams, что сообщение чата удаляется из-за политики хранения Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Пользователь в Teams, объясняющий, что сообщения удаляются в результате политики хранения Teams":::

<span data-ttu-id="4ce57-140">Для сообщений канала конечные пользователи (участники канала) будут видеть, что удаленные сообщения исчезают из вида после истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="4ce57-140">For Channel messages, the end users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="4ce57-141">Если удаленное сообщение является родительским сообщением цепочки бесед, то на месте родительского сообщения будет отображаться сообщение "Это сообщение было удалено из-за политики хранения".</span><span class="sxs-lookup"><span data-stu-id="4ce57-141">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="Снимок экрана: канал перед хранением":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Снимок экрана: канал после хранения":::

> [!NOTE]
> <span data-ttu-id="4ce57-144">Сообщения, отображаемые конечными пользователями в результате удаления сообщений, в настоящее время не настраиваются.</span><span class="sxs-lookup"><span data-stu-id="4ce57-144">The displayed messages that end users see as a result of deleted messaging are not configurable at this time.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4ce57-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4ce57-145">Related topics</span></span>

- [<span data-ttu-id="4ce57-146">Начало работы с политиками хранения и метами хранения</span><span class="sxs-lookup"><span data-stu-id="4ce57-146">Get started with retention policies and retention labels</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="4ce57-147">Информация о хранении для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ce57-147">Learn about retention for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="4ce57-148">Создание и настройка политик хранения</span><span class="sxs-lookup"><span data-stu-id="4ce57-148">Create and configure retention policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)