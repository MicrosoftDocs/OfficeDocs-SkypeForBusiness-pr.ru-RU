---
title: Страница установки параметров базы данных
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Настраиваются дополнительные параметры размещения файлов базы данных и журналов в SQL Server. Доступны перечисленные ниже варианты.
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806919"
---
# <a name="install-database-options-page"></a><span data-ttu-id="a1752-104">Страница параметров установки базы данных</span><span class="sxs-lookup"><span data-stu-id="a1752-104">Install Database Options Page</span></span>

<span data-ttu-id="a1752-105">Настраиваются дополнительные параметры размещения файлов базы данных и журналов в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1752-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="a1752-106">Доступны перечисленные ниже варианты.</span><span class="sxs-lookup"><span data-stu-id="a1752-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1752-107">Выберите вариант, который наилучшим образом соответствует вашим требованиям и политикам, относящийся к размещению данных и файлов журнала на SQL Server компьютерах.</span><span class="sxs-lookup"><span data-stu-id="a1752-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="a1752-108">**Автоматически определять расположение** файла базы данных: по умолчанию используется алгоритм, который определяет доступное пространство на SQL Server и распределяет файлы базы данных и журналов для оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="a1752-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="a1752-109">**Используйте SQL Server экземпляра** по умолчанию: выберите этот параметр, чтобы разместить файлы базы данных и журналов на основе параметров экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1752-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="a1752-110">Эти параметры обычно настраиваются и управляются администратором баз данных.</span><span class="sxs-lookup"><span data-stu-id="a1752-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="a1752-111">**Мы** перейдите по этому пути на целевом SQL Server: выберите этот параметр, чтобы определить собственные пути для файлов SQL Server базы данных и журналов, введя полный путь к диску и папке, в которой будут размещены файлы базы данных и журналов.</span><span class="sxs-lookup"><span data-stu-id="a1752-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1752-112">Вводимые пути могут быть изменены в соответствии с алгоритмами оптимизации производительности, действующими в установке.</span><span class="sxs-lookup"><span data-stu-id="a1752-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="a1752-113">Дополнительные сведения см. в разделе [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span><span class="sxs-lookup"><span data-stu-id="a1752-113">For details, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span></span>

 <span data-ttu-id="a1752-114">**ОК**: нажмите кнопку "ОК", чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="a1752-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="a1752-115">**Отмена**: нажмите кнопку "Отмена", чтобы отменить все изменения и вернуться на экран "Установка базы данных".</span><span class="sxs-lookup"><span data-stu-id="a1752-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="a1752-116">**Справка**: нажмите кнопку "Справка" для перехода на страницу справки.</span><span class="sxs-lookup"><span data-stu-id="a1752-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1752-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a1752-117">See also</span></span>

[<span data-ttu-id="a1752-118">Размещение данных и файла журнала SQL Server</span><span class="sxs-lookup"><span data-stu-id="a1752-118">SQL Server Data and Log File Placement</span></span>](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
