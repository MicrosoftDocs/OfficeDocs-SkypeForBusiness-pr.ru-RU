---
title: Известные проблемы с политиками хранения в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Текущий список известных проблем для политик хранения в Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838209"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="074ee-103">Известные проблемы с политиками хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="074ee-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="074ee-104">Мы пока не поддерживаем конфигурацию для хранения сообщений частных каналов.</span><span class="sxs-lookup"><span data-stu-id="074ee-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="074ee-105">Поддерживается хранение файлов, общих для частных каналов.</span><span class="sxs-lookup"><span data-stu-id="074ee-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="074ee-106">Ниже описаны известные проблемы, возникающие при работе с политиками хранения в группах, которые отслеживаются и изучаются.</span><span class="sxs-lookup"><span data-stu-id="074ee-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="074ee-107">В разделе выбор команд в строке расположение сообщений канала Teams могут отображаться группы Office 365, которые не являются группами.</span><span class="sxs-lookup"><span data-stu-id="074ee-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="074ee-108">Это будет решено в будущем.</span><span class="sxs-lookup"><span data-stu-id="074ee-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="074ee-109">В разделе Выбор пользователей в строке расположение чата Teams могут отображаться гости и пользователи без почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="074ee-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="074ee-110">Политики хранения не предназначены для гостей, и мы работаем над ее удалением из списка.</span><span class="sxs-lookup"><span data-stu-id="074ee-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="074ee-111">Помощник по жизненному циклу Exchange (ЕЛК) запускается ежедневно, но у него есть соглашение об уровне обслуживания в течение 7 дней.</span><span class="sxs-lookup"><span data-stu-id="074ee-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="074ee-112">Как следствие, возможно, что если у вас есть политика хранения в Teams для удаления элементов старше 60 дней, эти элементы могут храниться не более чем в 67 дня.</span><span class="sxs-lookup"><span data-stu-id="074ee-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="074ee-113">Это не новая ситуация — она следует за моделью Exchange.</span><span class="sxs-lookup"><span data-stu-id="074ee-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="074ee-114">Разумеется, в большинстве случаев задержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="074ee-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Значок, представляющий точку принятия решения](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="074ee-116">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="074ee-116">Decision point</span></span>         |<span data-ttu-id="074ee-117">Какие функции по обеспечению безопасности и соответствия нужны вашей организации?</span><span class="sxs-lookup"><span data-stu-id="074ee-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="074ee-118">Есть ли у вашей организации лицензии для удовлетворения бизнес-требований по безопасности и соответствию?</span><span class="sxs-lookup"><span data-stu-id="074ee-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Значок, представляющий следующие шаги](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="074ee-120">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="074ee-120">Next steps</span></span>         |<span data-ttu-id="074ee-121">Задокументируйте необходимые функции безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="074ee-121">Document your required security and compliance features.</span></span>         |
