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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a7dd5bac7c82814befab66247b1bfa8cf4943f6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569966"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="41d9a-103">Известные проблемы с политиками хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="41d9a-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="41d9a-104">Ниже описаны известные проблемы, возникающие при работе с политиками хранения в группах, которые отслеживаются и изучаются.</span><span class="sxs-lookup"><span data-stu-id="41d9a-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="41d9a-105">В разделе выбор команд в строке расположение сообщений канала Teams могут отображаться группы Office 365, которые не являются группами.</span><span class="sxs-lookup"><span data-stu-id="41d9a-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="41d9a-106">Это будет решено в будущем.</span><span class="sxs-lookup"><span data-stu-id="41d9a-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="41d9a-107">В разделе Выбор пользователей в строке расположение чата Teams могут отображаться гости и пользователи без почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="41d9a-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="41d9a-108">Политики хранения не предназначены для гостей, и мы работаем над ее удалением из списка.</span><span class="sxs-lookup"><span data-stu-id="41d9a-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="41d9a-109">Помощник по жизненному циклу Exchange (ЕЛК) запускается ежедневно, но у него есть соглашение об уровне обслуживания в течение 7 дней.</span><span class="sxs-lookup"><span data-stu-id="41d9a-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="41d9a-110">Как следствие, возможно, что если у вас есть политика хранения в Teams для удаления элементов старше 60 дней, эти элементы могут храниться не более чем в 67 дня.</span><span class="sxs-lookup"><span data-stu-id="41d9a-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="41d9a-111">Это не новая ситуация — она следует за моделью Exchange.</span><span class="sxs-lookup"><span data-stu-id="41d9a-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="41d9a-112">Разумеется, в большинстве случаев задержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="41d9a-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Значок, представляющий точку принятия решения](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="41d9a-114">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="41d9a-114">Decision point</span></span>         |<span data-ttu-id="41d9a-115">Какие функции по обеспечению безопасности и соответствия нужны вашей организации?</span><span class="sxs-lookup"><span data-stu-id="41d9a-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="41d9a-116">Есть ли у вашей организации лицензии для удовлетворения бизнес-требований по безопасности и соответствию?</span><span class="sxs-lookup"><span data-stu-id="41d9a-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Значок, представляющий следующие шаги](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="41d9a-118">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="41d9a-118">Next steps</span></span>         |<span data-ttu-id="41d9a-119">Задокументируйте необходимые функции безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="41d9a-119">Document your required security and compliance features.</span></span>         |
