---
title: Политики управления приложениями AppLocker в Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Сведения о том, как включить клиентские приложения Teams для настольных систем с политиками управления приложениями AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb12012c0775d98c7d1b08b61c6c0deba83a4d5f
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516777"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="2c2b8-103">Политики управления приложениями AppLocker в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2c2b8-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="2c2b8-104">В этой статье объясняется, как включить клиентское приложение Teams для настольных систем с политиками управления приложениями AppLocker.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="2c2b8-105">Функция AppLocker разработана для ограничения выполнения программы и сценария пользователями, не являющимися администраторами.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="2c2b8-106">Дополнительные сведения и рекомендации по AppLocker можно найти в статье [что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="2c2b8-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="2c2b8-107">Процесс включения команд с помощью AppLocker требует создания политик брандмауэров на основе AppLocker.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="2c2b8-108">Политики создаются с помощью программного обеспечения управления групповыми политиками и/или с помощью командлетов Windows PowerShell для AppLocker (Дополнительные сведения можно найти в [техническом справочнике по AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) ).</span><span class="sxs-lookup"><span data-stu-id="2c2b8-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="2c2b8-109">Политика AppLocker сохраняется в формате XML и может быть изменена любым текстовым или XML-редактором.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="2c2b8-110">Teams брандмауэров с AppLocker</span><span class="sxs-lookup"><span data-stu-id="2c2b8-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="2c2b8-111">Правила AppLocker организованы в коллекции правил.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="2c2b8-112">Правила AppLocker применяются к целевому приложению и представляют собой компоненты, составляющие политику AppLocker.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="2c2b8-113">Для Добавление Teams рекомендуется использовать [правила условия издателя](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , так как все файлы приложения Teams снабжены цифровой подписью.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="2c2b8-114">Мы не рекомендуем использовать правила путей, так как каталог установки Teams является доступным для записи пользователем.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="2c2b8-115">Кроме того, мы не рекомендуем использовать правила для хеша, поскольку правила должны обновляться каждый раз при обновлении клиентского приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="2c2b8-116">Так как на настольных компьютерах Teams с цифровой подписью, условие издателя определяет файл приложения на основе его цифровой подписи и атрибутов внедренной версии.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="2c2b8-117">Цифровая подпись включает сведения о компании, которая создала файл приложения (издатель).</span><span class="sxs-lookup"><span data-stu-id="2c2b8-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="2c2b8-118">Сведения о версии, получаемые из двоичного ресурса, включают имя продукта, частью которого является файл, и номер версии файла приложения.</span><span class="sxs-lookup"><span data-stu-id="2c2b8-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="2c2b8-119">Пример правил условий в Publisher</span><span class="sxs-lookup"><span data-stu-id="2c2b8-119">Example of publisher condition rules</span></span>

<span data-ttu-id="2c2b8-120">Для клиентского приложения Teams (все файлы, все версии):</span><span class="sxs-lookup"><span data-stu-id="2c2b8-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="2c2b8-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2c2b8-121">Related topics</span></span>
<span data-ttu-id="2c2b8-122">[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Технический справочник по AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="2c2b8-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>