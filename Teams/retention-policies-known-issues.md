---
title: Известные проблемы с политиками хранения в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Текущий список известные проблемы с группами Майкрософт политики хранения.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dca7decd2c3c051c0d56a14e2a2d1485b777f92e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205504"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="2435d-103">Известные проблемы с политиками хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2435d-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="2435d-104">Следующие указаны известные проблемы, возникающие при политики хранения в группах, которые они отслеживаемые и изучению.</span><span class="sxs-lookup"><span data-stu-id="2435d-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="2435d-105">В разделе Выбор групп в строке расположение канала группы сообщений может появиться группы Office 365, которые не также групп.</span><span class="sxs-lookup"><span data-stu-id="2435d-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="2435d-106">Это будет направлено в будущем.</span><span class="sxs-lookup"><span data-stu-id="2435d-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="2435d-107">В разделе Выбор пользователей в строке расположение группы чата может появиться Гости и не являющиеся почтовых ящиков пользователей.</span><span class="sxs-lookup"><span data-stu-id="2435d-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="2435d-108">Политики хранения не предназначены для Гости, и мы работаем, чтобы удалить их из списка.</span><span class="sxs-lookup"><span data-stu-id="2435d-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="2435d-109">Помощник по Exchange жизненного цикла (ELC) запускается ежедневно, но имеет соглашение об УРОВНЕ 7 дней.</span><span class="sxs-lookup"><span data-stu-id="2435d-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="2435d-110">В результате это и возможно, что при наличии политику хранения групп удалять элементы старше 60 дней, эти элементы могут сохранения 67 дней.</span><span class="sxs-lookup"><span data-stu-id="2435d-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="2435d-111">Это не новые ситуации - его следует модели Exchange.</span><span class="sxs-lookup"><span data-stu-id="2435d-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="2435d-112">Конечно в большинстве случаев нет без задержки.</span><span class="sxs-lookup"><span data-stu-id="2435d-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Значок для точки принятия решений.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="2435d-114">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="2435d-114">Decision point</span></span>         |<span data-ttu-id="2435d-115">Какие функции по обеспечению безопасности и соответствия нужны вашей организации?</span><span class="sxs-lookup"><span data-stu-id="2435d-115">What security and compliance features does your organization require?</span></span> <span data-ttu-id="2435d-116">Есть ли у вашей организации лицензии для удовлетворения бизнес-требований по безопасности и соответствию?</span><span class="sxs-lookup"><span data-stu-id="2435d-116">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Значок дальнейших действий.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="2435d-118">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="2435d-118">Next steps</span></span>         |<span data-ttu-id="2435d-119">Документирование вашей необходимые компоненты безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="2435d-119">Document your required security and compliance features.</span></span>         |
