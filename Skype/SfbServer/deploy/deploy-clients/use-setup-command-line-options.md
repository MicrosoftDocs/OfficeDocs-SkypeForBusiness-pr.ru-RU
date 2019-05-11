---
title: Использование параметров командной строки программы установки с Скайп пользователей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Сводка: Сведения об операциях командной строки Setup.exe в программе установки Office.'
ms.openlocfilehash: 924ecab4a53c6ec591416661bc98078e8e48381c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895063"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="824d4-103">Использование параметров командной строки программы установки с Скайп пользователей</span><span class="sxs-lookup"><span data-stu-id="824d4-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="824d4-104">**Сводка:** Узнайте об операциях командной строки Setup.exe в программе установки Office.</span><span class="sxs-lookup"><span data-stu-id="824d4-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="824d4-105">Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office.</span><span class="sxs-lookup"><span data-stu-id="824d4-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="824d4-106">Вместо использования параметров командной строки программы установки, обычно используется центр развертывания Office и файл Config.xml для настройки программы установки и компонентов продукта.</span><span class="sxs-lookup"><span data-stu-id="824d4-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="824d4-107">Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="824d4-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="824d4-108">**Параметры командной строки программы установки Office**</span><span class="sxs-lookup"><span data-stu-id="824d4-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="824d4-109">**Параметр командной строки программы установки**</span><span class="sxs-lookup"><span data-stu-id="824d4-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="824d4-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="824d4-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="824d4-111">/admin</span><span class="sxs-lookup"><span data-stu-id="824d4-111">/admin</span></span>  <br/> |<span data-ttu-id="824d4-112">Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</span><span class="sxs-lookup"><span data-stu-id="824d4-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="824d4-113">/adminfile [путь]</span><span class="sxs-lookup"><span data-stu-id="824d4-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="824d4-p102">Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</span><span class="sxs-lookup"><span data-stu-id="824d4-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="824d4-116">/config [путь]</span><span class="sxs-lookup"><span data-stu-id="824d4-116">/config [path]</span></span>  <br/> |<span data-ttu-id="824d4-117">Указывает файл Config.xml, который программа установки использует во время установки.</span><span class="sxs-lookup"><span data-stu-id="824d4-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="824d4-118">Используйте параметр/config для указания файла Config.xml, настроенные для Скайп для установок бизнеса, например:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="824d4-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="824d4-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="824d4-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="824d4-120">Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office.</span><span class="sxs-lookup"><span data-stu-id="824d4-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="824d4-121">Например, можно использовать / modify параметр, чтобы добавить или удалить Скайп для функций бизнес.</span><span class="sxs-lookup"><span data-stu-id="824d4-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="824d4-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="824d4-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="824d4-123">Запускает программу установки на компьютере пользователя для восстановления Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="824d4-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="824d4-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="824d4-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="824d4-125">Запускает программу установки для удаления Скайп для бизнеса с компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="824d4-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


