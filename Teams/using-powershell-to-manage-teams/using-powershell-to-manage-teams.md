---
title: Управление группами с помощью PowerShell
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Научитесь использовать Windows PowerShell для управления все функции, доступные в группами Майкрософт.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3deddb614be2ad5ee1389dcf53d8dab749a8567b
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855647"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="bb92d-103">Управление группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb92d-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="bb92d-104">Функции в группах можно управлять с помощью PowerShell или группами Майкрософт и Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bb92d-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="bb92d-105">! [Примечание] Не все компоненты в группах можно управлять с помощью модуля соединителя группы.</span><span class="sxs-lookup"><span data-stu-id="bb92d-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="bb92d-106">Может потребоваться использовать Скайп для Business connector.</span><span class="sxs-lookup"><span data-stu-id="bb92d-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="bb92d-107">Просмотреть [загрузить и установить Скайп для бизнеса в Интернет соединителя](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="bb92d-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="bb92d-108">Шаг 1: предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bb92d-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="bb92d-109">Удаленное управление группами Майкрософт с помощью PowerShell поддерживается только в 64-разрядных компьютеров под управлением одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="bb92d-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="bb92d-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bb92d-110">Windows 10</span></span>
- <span data-ttu-id="bb92d-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="bb92d-111">Windows 8.1</span></span>
- <span data-ttu-id="bb92d-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="bb92d-112">Windows 8</span></span> 
- <span data-ttu-id="bb92d-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bb92d-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="bb92d-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bb92d-114">Windows Server 2012</span></span>
- <span data-ttu-id="bb92d-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="bb92d-115">Windows Server 2008</span></span>
- <span data-ttu-id="bb92d-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="bb92d-116">Windows 7</span></span>
    
<span data-ttu-id="bb92d-117">В дополнение к поддерживаемая операционная система на компьютере необходимо также работать следующие:</span><span class="sxs-lookup"><span data-stu-id="bb92d-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="bb92d-118">PowerShell 3.0 или выше</span><span class="sxs-lookup"><span data-stu-id="bb92d-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="bb92d-119">Модуль PowerShell соединителя группы</span><span class="sxs-lookup"><span data-stu-id="bb92d-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="bb92d-120">Шаг 2: Install PowerShell 3.0 или выше</span><span class="sxs-lookup"><span data-stu-id="bb92d-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="bb92d-121">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="bb92d-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="bb92d-122">Шаг 3: Загрузите и установите модуль соединителя группы</span><span class="sxs-lookup"><span data-stu-id="bb92d-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="bb92d-123">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="bb92d-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="bb92d-124">Ниже приводится ссылка для загрузки из Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="bb92d-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="bb92d-125">Шаг 4: Подключиться, используя модуль соединителя группы</span><span class="sxs-lookup"><span data-stu-id="bb92d-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="bb92d-126">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="bb92d-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="bb92d-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="bb92d-127">Related topics</span></span>
- [<span data-ttu-id="bb92d-128">Управление группами функций с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb92d-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)