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
description: Узнайте, как включить клиентские приложения Teams для настольных пк с помощью политик управления приложениями AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e70fc4502851137494c316db9eff7faefc140d1
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526695"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="90aff-103">Политики управления приложениями AppLocker в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90aff-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="90aff-104">В этой статье объясняется, как включить клиентские приложения Teams с помощью политик управления приложениями AppLocker.</span><span class="sxs-lookup"><span data-stu-id="90aff-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="90aff-105">Использование AppLocker предназначено для ограничения выполнения программ и сценариев пользователями, не относясь к администраторам.</span><span class="sxs-lookup"><span data-stu-id="90aff-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="90aff-106">Дополнительные сведения и инструкции по AppLocker см. в руководстве [по appLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)</span><span class="sxs-lookup"><span data-stu-id="90aff-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="90aff-107">Для включения Teams с помощью AppLocker необходимо создать политики включения в список на основе AppLocker.</span><span class="sxs-lookup"><span data-stu-id="90aff-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="90aff-108">Политики создаются с помощью программного обеспечения для управления групповыми политиками и (или) использования Windows PowerShell для AppLocker (дополнительные сведения см. в технической справке [по AppLocker).](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="90aff-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="90aff-109">Политика AppLocker сохранена в формате XML и может быть изменена с помощью любого текста или редактора XML.</span><span class="sxs-lookup"><span data-stu-id="90aff-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="90aff-110">Список "Разрешить" в Teams с помощью AppLocker</span><span class="sxs-lookup"><span data-stu-id="90aff-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="90aff-111">Правила AppLocker организованы в коллекции правил.</span><span class="sxs-lookup"><span data-stu-id="90aff-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="90aff-112">Правила AppLocker применяются к целевому приложению, и именно они являются компонентами, составляющими политику AppLocker.</span><span class="sxs-lookup"><span data-stu-id="90aff-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="90aff-113">Чтобы разрешить Teams, рекомендуем использовать правила условий [publisher,](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) так как все файлы приложений Teams имеют цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="90aff-113">To allow Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="90aff-114">Не рекомендуется использовать правила путей, так как каталог установки Teams можно писать пользователям.</span><span class="sxs-lookup"><span data-stu-id="90aff-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="90aff-115">Мы также не рекомендуем использовать hash rules, так как они должны обновляться при каждом обновлении клиентского приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="90aff-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="90aff-116">Так как исполняемые файлы рабочего стола Teams имеют цифровую подпись, в условии publisher указывается файл приложения на основе цифровой подписи и атрибутов внедренной версии.</span><span class="sxs-lookup"><span data-stu-id="90aff-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="90aff-117">Цифровая подпись содержит сведения о компании, создав файл приложения (издателе).</span><span class="sxs-lookup"><span data-stu-id="90aff-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="90aff-118">Сведения о версии, полученные из двоичного ресурса, включают имя продукта, в состав которого входит файл, и номер версии файла приложения.</span><span class="sxs-lookup"><span data-stu-id="90aff-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="90aff-119">Пример правил условий publisher</span><span class="sxs-lookup"><span data-stu-id="90aff-119">Example of publisher condition rules</span></span>

<span data-ttu-id="90aff-120">Для клиентского приложения Teams (все файлы, все версии) добавьте в правила DLL для исполняемых & следующее:</span><span class="sxs-lookup"><span data-stu-id="90aff-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="90aff-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="90aff-121">Related topics</span></span>
<span data-ttu-id="90aff-122">[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Справочник по приложению AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="90aff-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>
