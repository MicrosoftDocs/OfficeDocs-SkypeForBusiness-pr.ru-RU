---
title: Страница установки параметров базы данных
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: Вы настраиваете дополнительные параметры размещения файлов базы данных и журналов на сервере SQL Server. Доступны перечисленные ниже варианты.
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215310"
---
# <a name="install-database-options-page"></a><span data-ttu-id="a5d2c-104">Страница установки параметров базы данных</span><span class="sxs-lookup"><span data-stu-id="a5d2c-104">Install Database Options Page</span></span>

<span data-ttu-id="a5d2c-105">Вы настраиваете дополнительные параметры размещения файлов базы данных и журналов на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="a5d2c-106">Доступны перечисленные ниже варианты.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5d2c-107">Выберите параметр, который наилучшим образом соответствует требованиям и политикам, относящимся к размещению файлов данных и журналов на компьютерах SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="a5d2c-108">**Автоматически определять местоположение файла базы данных**: параметр по умолчанию использует алгоритм, определяющий доступное пространство на SQL Server и распространяющий файлы базы данных и журналов для обеспечения оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="a5d2c-109">**Использовать значения по умолчанию для экземпляра SQL Server**: Выберите этот параметр, чтобы поместить файлы базы данных и журналов в соответствии с параметрами экземпляра на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="a5d2c-110">Эти параметры обычно настраиваются и управляются администратором баз данных.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="a5d2c-111">**Мы будем использовать следующий путь на целевом сервере SQL Server**: Выберите этот параметр, чтобы определить собственные пути для базы данных SQL Server и файлов журналов, указав полный путь к диску и папке, где будут размещаться базы данных и файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5d2c-112">Вводимые пути могут быть изменены в соответствии с алгоритмами оптимизации производительности, действующими в установке.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="a5d2c-113">Дополнительные сведения см. в разделе [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span><span class="sxs-lookup"><span data-stu-id="a5d2c-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="a5d2c-114">**ОК**: нажмите кнопку "ОК", чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="a5d2c-115">**Отмена**: нажмите кнопку "Отмена", чтобы отменить все изменения и вернуться на экран "Установка базы данных".</span><span class="sxs-lookup"><span data-stu-id="a5d2c-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="a5d2c-116">**Справка**: нажмите кнопку "Справка" для перехода на страницу справки.</span><span class="sxs-lookup"><span data-stu-id="a5d2c-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5d2c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a5d2c-117">See also</span></span>

[<span data-ttu-id="a5d2c-118">Размещение данных и файла журнала SQL Server</span><span class="sxs-lookup"><span data-stu-id="a5d2c-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
