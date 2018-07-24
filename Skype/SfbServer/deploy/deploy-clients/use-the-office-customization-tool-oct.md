---
title: Использование центра развертывания Office (OCT) в Скайп для Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Сводка: Способы использования центра развертывания Office с Скайп для клиента Business.'
ms.openlocfilehash: bee037e005a9887a3f338ef071bec6fddc8990ea
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983709"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="9137a-103">Использование центра развертывания Office (OCT) в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9137a-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="9137a-104">**Сводка:** Как использовать центр развертывания Office с Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="9137a-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="9137a-105">Центр развертывания Office входит в состав программы установки и является рекомендованным средством для многих видов настройки.</span><span class="sxs-lookup"><span data-stu-id="9137a-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="9137a-106">С помощью центра развертывания Office можно настроить Office и сохранить настройки установки в MSP-файле.</span><span class="sxs-lookup"><span data-stu-id="9137a-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="9137a-107">Этот файл можно поместить в папку "Updates" в точке сетевой установки.</span><span class="sxs-lookup"><span data-stu-id="9137a-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="9137a-108">Во время установки Office программа установки выполняет поиск файла настроек установки в папке "Updates" и применяет эти настройки.</span><span class="sxs-lookup"><span data-stu-id="9137a-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="9137a-109">Папки "Updates" используется только для развертывания обновлений программного обеспечения при начальной установке Office.</span><span class="sxs-lookup"><span data-stu-id="9137a-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="9137a-110">Центр развертывания Office является частью программы установки и она используется только для корпоративных версиях продукта.</span><span class="sxs-lookup"><span data-stu-id="9137a-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="9137a-111">Запустите центр развертывания Office с помощью следующей команды `setup.exe /admin` в командной строке из корневого каталога точки сетевой установки, который содержит Office исходные файлы.</span><span class="sxs-lookup"><span data-stu-id="9137a-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="9137a-112">Например, используйте следующий путь.</span><span class="sxs-lookup"><span data-stu-id="9137a-112">For example, use the following:</span></span>
  
 ```
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="9137a-113">Администраторы используют центр развертывания Office для создания MSP-файл программы установки и можно настроить следующие области:</span><span class="sxs-lookup"><span data-stu-id="9137a-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="9137a-114">**Программа установки** Используется для указания место установки по умолчанию на название организации клиента и по умолчанию, дополнительные сетевые источники установки, ключ продукта, лицензионное соглашение, Отображение уровня, более ранних версий Office для удаления, настраиваемые программы для запуска во время Установка параметров безопасности и свойств установки.</span><span class="sxs-lookup"><span data-stu-id="9137a-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="9137a-115">**Функции** Используется для настройки параметров пользователя и для настройки способа установки компонентов Office.</span><span class="sxs-lookup"><span data-stu-id="9137a-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="9137a-116">С помощью центра развертывания Office администратор может указать первоначальные значения по умолчанию для пользовательских параметров приложений Office.</span><span class="sxs-lookup"><span data-stu-id="9137a-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="9137a-117">После установки пользователи могут изменить большинство из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="9137a-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="9137a-118">**Дополнительное содержимое** Используется для добавления или удаления файлов, добавление или удаление записей реестра и настройки ярлыков.</span><span class="sxs-lookup"><span data-stu-id="9137a-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="9137a-119">**Outlook** Используется для настройки профиля пользователя по умолчанию в Outlook, указания параметров Exchange, добавление учетных записей, удаление учетных записей и экспорт параметров и указания групп отправки и получения.</span><span class="sxs-lookup"><span data-stu-id="9137a-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="9137a-120">Сведения о центре развертывания Office, в разделе [использования центра развертывания Office для настройки Office 2013](https://docs.microsoft.com/en-us/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="9137a-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/en-us/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="9137a-121">Обратите внимание, что эти сведения также относится к более поздние версии Office.</span><span class="sxs-lookup"><span data-stu-id="9137a-121">Note that this information also applies to later versions of Office.</span></span>
  

