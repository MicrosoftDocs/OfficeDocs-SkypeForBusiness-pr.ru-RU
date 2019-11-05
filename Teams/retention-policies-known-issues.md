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
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968340"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="f5b15-103">Известные проблемы с политиками хранения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5b15-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="f5b15-104">Мы пока не поддерживаем конфигурацию для хранения сообщений частных каналов.</span><span class="sxs-lookup"><span data-stu-id="f5b15-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="f5b15-105">Поддерживается хранение файлов, общих для частных каналов.</span><span class="sxs-lookup"><span data-stu-id="f5b15-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="f5b15-106">Ниже описаны известные проблемы, возникающие при работе с политиками хранения в группах, которые отслеживаются и изучаются.</span><span class="sxs-lookup"><span data-stu-id="f5b15-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="f5b15-107">В разделе выбор команд в строке расположение сообщений канала Teams могут отображаться группы Office 365, которые не являются группами.</span><span class="sxs-lookup"><span data-stu-id="f5b15-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="f5b15-108">Это будет решено в будущем.</span><span class="sxs-lookup"><span data-stu-id="f5b15-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="f5b15-109">В разделе Выбор пользователей в строке расположение чата Teams могут отображаться гости и пользователи без почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="f5b15-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="f5b15-110">Политики хранения не предназначены для гостей, и мы работаем над ее удалением из списка.</span><span class="sxs-lookup"><span data-stu-id="f5b15-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="f5b15-111">Помощник по жизненному циклу Exchange (ЕЛК) запускается ежедневно, но у него есть соглашение об уровне обслуживания в течение 7 дней.</span><span class="sxs-lookup"><span data-stu-id="f5b15-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="f5b15-112">Как следствие, возможно, что если у вас есть политика хранения в Teams для удаления элементов старше 60 дней, эти элементы могут храниться не более чем в 67 дня.</span><span class="sxs-lookup"><span data-stu-id="f5b15-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="f5b15-113">Это не новая ситуация — она следует за моделью Exchange.</span><span class="sxs-lookup"><span data-stu-id="f5b15-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="f5b15-114">Разумеется, в большинстве случаев задержка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f5b15-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Значок, представляющий точку принятия решения](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="f5b15-116">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="f5b15-116">Decision point</span></span>         |<span data-ttu-id="f5b15-117">Какие функции по обеспечению безопасности и соответствия нужны вашей организации?</span><span class="sxs-lookup"><span data-stu-id="f5b15-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="f5b15-118">Есть ли у вашей организации лицензии для удовлетворения бизнес-требований по безопасности и соответствию?</span><span class="sxs-lookup"><span data-stu-id="f5b15-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Значок, представляющий следующие шаги](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="f5b15-120">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="f5b15-120">Next steps</span></span>         |<span data-ttu-id="f5b15-121">Задокументируйте необходимые функции безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f5b15-121">Document your required security and compliance features.</span></span>         |
