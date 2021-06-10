---
title: Политики управления AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как включить Teams с помощью политик управления приложенияМи AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120851"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="ce79a-103">Политики управления приложениями AppLocker в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce79a-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="ce79a-104">В этой статье объясняется, как включить Teams с помощью политик управления приложениями AppLocker.</span><span class="sxs-lookup"><span data-stu-id="ce79a-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="ce79a-105">Приложение AppLocker предназначено для ограничения выполнения программ и сценариев пользователями, не относясь к администрированию.</span><span class="sxs-lookup"><span data-stu-id="ce79a-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="ce79a-106">Дополнительные сведения и инструкции по AppLocker см. в приложении [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)</span><span class="sxs-lookup"><span data-stu-id="ce79a-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="ce79a-107">Для включения Teams с помощью AppLocker необходимо создать политики списка на основе AppLocker.</span><span class="sxs-lookup"><span data-stu-id="ce79a-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="ce79a-108">Политики создаются с помощью программного обеспечения для управления групповыми политиками и /или использования Windows PowerShell для AppLocker (дополнительные сведения см. в технической справке [AppLocker).](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="ce79a-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="ce79a-109">Политика AppLocker сохранена в формате XML и может быть изменена с помощью любого текста или редактора XML.</span><span class="sxs-lookup"><span data-stu-id="ce79a-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="ce79a-110">Teams списка разрешить с помощью AppLocker</span><span class="sxs-lookup"><span data-stu-id="ce79a-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="ce79a-111">Правила AppLocker организованы в наборы правил.</span><span class="sxs-lookup"><span data-stu-id="ce79a-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="ce79a-112">Правила AppLocker применяются к целевому приложению, и они являются компонентами, которые составляют политику AppLocker.</span><span class="sxs-lookup"><span data-stu-id="ce79a-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="ce79a-113">Чтобы разрешить Teams, рекомендуется использовать правила [](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) условий publisher, так как Teams все файлы приложений подписаны цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="ce79a-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="ce79a-114">Использовать правила пути не рекомендуется, так как Teams каталог установки является удобным для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ce79a-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="ce79a-115">Мы также не рекомендуем использовать правила с hash, так как они должны обновляться при каждом обновлении Teams клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="ce79a-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="ce79a-116">Поскольку Teams файлам на компьютере назначена цифровая подпись, в условии publisher указывается файл приложения на основе его цифровой подписи и внедренных атрибутов версии.</span><span class="sxs-lookup"><span data-stu-id="ce79a-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="ce79a-117">Цифровая подпись содержит сведения о компании, создав файл приложения (издателя).</span><span class="sxs-lookup"><span data-stu-id="ce79a-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="ce79a-118">Сведения о версии, полученные из двоичного ресурса, включают имя продукта, в состав которого входит файл, и номер версии файла приложения.</span><span class="sxs-lookup"><span data-stu-id="ce79a-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="ce79a-119">Пример правил условий publisher</span><span class="sxs-lookup"><span data-stu-id="ce79a-119">Example of publisher condition rules</span></span>

<span data-ttu-id="ce79a-120">Для клиента Teams (все файлы, все версии) добавьте в правила DLL исполняемые правила &:</span><span class="sxs-lookup"><span data-stu-id="ce79a-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="ce79a-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ce79a-121">Related topics</span></span>
<span data-ttu-id="ce79a-122">[Что такое AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Техническая справка по AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="ce79a-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>