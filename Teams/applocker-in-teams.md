---
title: Политики управления приложениями AppLocker в группах Майкрософт
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Процедура включения рабочего стола клиентское приложение группы с политиками управления AppLocker приложений.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063214"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="03df0-103">Политики управления приложениями AppLocker в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="03df0-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="03df0-104">В этой статье объясняется, как включить приложения для настольных компьютеров группы с политиками управления AppLocker приложений.</span><span class="sxs-lookup"><span data-stu-id="03df0-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="03df0-105">Использование AppLocker предназначен для ограничения выполнение программы и скрипт пользователям без прав администратора.</span><span class="sxs-lookup"><span data-stu-id="03df0-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="03df0-106">Дополнительные сведения и инструкции по AppLocker см [возможности AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span><span class="sxs-lookup"><span data-stu-id="03df0-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="03df0-107">Процесс для включения групп с помощью AppLocker требует создания политик на основе AppLocker создания списка разрешенных.</span><span class="sxs-lookup"><span data-stu-id="03df0-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="03df0-108">Политики, созданные с помощью программного обеспечения управления групповой политики и/или использование командлетов Windows PowerShell для AppLocker ( [AppLocker Техническая справка](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) для получения дополнительных сведений см).</span><span class="sxs-lookup"><span data-stu-id="03df0-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="03df0-109">Политика AppLocker сохраняется в формате XML и можно изменить с помощью любого текстового или XML-редактора.</span><span class="sxs-lookup"><span data-stu-id="03df0-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="03df0-110">Разрабатывает групп с помощью AppLocker</span><span class="sxs-lookup"><span data-stu-id="03df0-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="03df0-111">Правила AppLocker сгруппированы в коллекции правил.</span><span class="sxs-lookup"><span data-stu-id="03df0-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="03df0-112">Они являются компонентами, которые составляют политики AppLocker и правила AppLocker применяются целевого приложения.</span><span class="sxs-lookup"><span data-stu-id="03df0-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="03df0-113">Группам белом рекомендуется использовать [publisher условие правила](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) , так как все файлы приложения группы используют цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="03df0-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="03df0-114">Не рекомендуется использовать путь правила, так как каталог установки групп для записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="03df0-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="03df0-115">Также не рекомендуется использовать правила хэш-функции из-за правил необходимо будет обновляться каждый раз, когда обновляется клиентского приложения группы.</span><span class="sxs-lookup"><span data-stu-id="03df0-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="03df0-116">Поскольку группам рабочего стола исполняемые файлы цифровую подпись, условие издателя указывает файл приложения на основе его цифровой подписи и атрибуты внедренных версии.</span><span class="sxs-lookup"><span data-stu-id="03df0-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="03df0-117">Цифровая подпись содержит сведения о компании, создавшей файла приложения (издатель).</span><span class="sxs-lookup"><span data-stu-id="03df0-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="03df0-118">Сведения о версии, получаемые из двоичного ресурса, включает в себя имя продукта, который является частью файла и номер версии файла приложения.</span><span class="sxs-lookup"><span data-stu-id="03df0-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="03df0-119">Пример publisher условие правила</span><span class="sxs-lookup"><span data-stu-id="03df0-119">Example of publisher condition rules</span></span>

<span data-ttu-id="03df0-120">Для клиентского приложения группы (все файлы, все версии):</span><span class="sxs-lookup"><span data-stu-id="03df0-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="03df0-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="03df0-121">Related topics</span></span>
<span data-ttu-id="03df0-122">[Что такое AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker Технический справочник](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="03df0-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>