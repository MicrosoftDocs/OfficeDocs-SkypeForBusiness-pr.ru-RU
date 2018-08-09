---
title: Управление группами с помощью PowerShell
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
description: Научитесь использовать Windows PowerShell для управления все функции, доступные в группами Майкрософт.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a83d6281352ca4ef6a5a8d57d3a27692c7288d6
ms.sourcegitcommit: 41e325c5440e26cc39a3c8945020f597f8dfac96
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "22213367"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="4f49b-103">Управление группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f49b-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="4f49b-104">Функции в группах можно управлять с помощью PowerShell или группами Майкрософт и Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4f49b-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="4f49b-105">! [Примечание] Не все компоненты в группах можно управлять с помощью модуля соединителя группы.</span><span class="sxs-lookup"><span data-stu-id="4f49b-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="4f49b-106">Может потребоваться использовать Скайп для Business connector.</span><span class="sxs-lookup"><span data-stu-id="4f49b-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="4f49b-107">Просмотреть [загрузить и установить Скайп для бизнеса в Интернет соединителя](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="4f49b-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="4f49b-108">Шаг 1: предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4f49b-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="4f49b-109">Удаленное управление группами Майкрософт с помощью PowerShell поддерживается только в 64-разрядных компьютеров под управлением одной из следующих операционных систем:</span><span class="sxs-lookup"><span data-stu-id="4f49b-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="4f49b-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4f49b-110">Windows 10</span></span>
- <span data-ttu-id="4f49b-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4f49b-111">Windows 8.1</span></span>
- <span data-ttu-id="4f49b-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4f49b-112">Windows 8</span></span> 
- <span data-ttu-id="4f49b-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4f49b-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="4f49b-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4f49b-114">Windows Server 2012</span></span>
- <span data-ttu-id="4f49b-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="4f49b-115">Windows Server 2008</span></span>
- <span data-ttu-id="4f49b-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="4f49b-116">Windows 7</span></span>
    
<span data-ttu-id="4f49b-117">В дополнение к поддерживаемая операционная система на компьютере необходимо также работать следующие:</span><span class="sxs-lookup"><span data-stu-id="4f49b-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="4f49b-118">PowerShell 3.0 или выше</span><span class="sxs-lookup"><span data-stu-id="4f49b-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="4f49b-119">Модуль PowerShell соединителя группы</span><span class="sxs-lookup"><span data-stu-id="4f49b-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="4f49b-120">Шаг 2: Install PowerShell 3.0 или выше</span><span class="sxs-lookup"><span data-stu-id="4f49b-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="4f49b-121">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="4f49b-121">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="4f49b-122">Шаг 3: Загрузите и установите модуль соединителя группы</span><span class="sxs-lookup"><span data-stu-id="4f49b-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="4f49b-123">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="4f49b-123">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="4f49b-124">Ниже приводится ссылка для загрузки из Isabella:https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="4f49b-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="4f49b-125">Шаг 4: Подключиться, используя модуль соединителя группы</span><span class="sxs-lookup"><span data-stu-id="4f49b-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="4f49b-126">Используйте этот раздел справки</span><span class="sxs-lookup"><span data-stu-id="4f49b-126">Use this topic for help</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="4f49b-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4f49b-127">Related topics</span></span>
- [<span data-ttu-id="4f49b-128">Управление группами функций с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f49b-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)