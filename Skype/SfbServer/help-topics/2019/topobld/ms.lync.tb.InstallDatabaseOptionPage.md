---
title: Страница установки параметров базы данных
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: Настраиваются расширенные параметры размещения баз данных и журнальных файлов в SQL Server. Доступны перечисленные ниже варианты.
ms.openlocfilehash: 4b4323f2b0e953ff24a458a2f28f75f52d4f0149
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121647"
---
# <a name="install-database-options-page"></a><span data-ttu-id="61521-104">Страница параметров установки базы данных</span><span class="sxs-lookup"><span data-stu-id="61521-104">Install Database Options Page</span></span>

<span data-ttu-id="61521-105">Настраиваются расширенные параметры размещения баз данных и журнальных файлов в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61521-105">You configure advanced options for the placement of database and log files on your SQL Server.</span></span> <span data-ttu-id="61521-106">Доступны перечисленные ниже варианты.</span><span class="sxs-lookup"><span data-stu-id="61521-106">The options available are:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61521-107">Выберите вариант, который наилучшим образом соответствует вашим требованиям и политикам, касающимся размещения данных и файлов журналов на SQL Server компьютерах.</span><span class="sxs-lookup"><span data-stu-id="61521-107">Select the option that best fits your requirements and policies pertaining to data and log file placement on your SQL Server computers.</span></span>

 <span data-ttu-id="61521-108">**Автоматически определите** расположение файлов базы данных. По умолчанию используется алгоритм, который определяет доступное пространство на SQL Server и распределяет файлы базы данных и журналов для оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="61521-108">**Automatically determine database file location**: The default option uses an algorithm that determines the available space on the SQL Server and distributes the database and log files for optimal performance.</span></span>

 <span data-ttu-id="61521-109">**Используйте SQL Server** по умолчанию: Выберите этот параметр для установки файлов баз данных и файлов журналов на основе параметров экземпляра в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61521-109">**Use SQL Server instance defaults**: Select this option to place database file and log files based on the instance settings at SQL Server.</span></span> <span data-ttu-id="61521-110">Эти параметры обычно настраиваются и управляются администратором баз данных.</span><span class="sxs-lookup"><span data-stu-id="61521-110">The options are typically managed and configured by your Database Administrator.</span></span>

 <span data-ttu-id="61521-111">**Мы** эти пути на целевом SQL Server : Выберите этот параметр, чтобы определить собственные пути для SQL Server базы данных и журналов, введя полный путь к диску и папке, где будут размещены базы данных и файлы журналов.</span><span class="sxs-lookup"><span data-stu-id="61521-111">**Us these path on target SQL Server**: Select this option to define your own paths for SQL Server database and log files by typing the full path to the drive and folder where the database and log files will be placed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61521-112">Вводимые пути могут быть изменены в соответствии с алгоритмами оптимизации производительности, действующими в установке.</span><span class="sxs-lookup"><span data-stu-id="61521-112">The paths that you enter may be modified based on performance optimization algorithms in the installation.</span></span> <span data-ttu-id="61521-113">Дополнительные сведения см. в разделе [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span><span class="sxs-lookup"><span data-stu-id="61521-113">For details, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).</span></span>

 <span data-ttu-id="61521-114">**ОК**: нажмите кнопку "ОК", чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="61521-114">**OK**: Click the OK button to commit your changes.</span></span>

 <span data-ttu-id="61521-115">**Отмена**: нажмите кнопку "Отмена", чтобы отменить все изменения и вернуться на экран "Установка базы данных".</span><span class="sxs-lookup"><span data-stu-id="61521-115">**Cancel**: Click Cancel to discard any changes and return to the Install Database screen.</span></span>

 <span data-ttu-id="61521-116">**Справка**: нажмите кнопку "Справка" для перехода на страницу справки.</span><span class="sxs-lookup"><span data-stu-id="61521-116">**Help**: Click the Help button to access this Help page.</span></span>

## <a name="see-also"></a><span data-ttu-id="61521-117">См. также</span><span class="sxs-lookup"><span data-stu-id="61521-117">See also</span></span>

[<span data-ttu-id="61521-118">Размещение данных и файла журнала SQL Server</span><span class="sxs-lookup"><span data-stu-id="61521-118">SQL Server Data and Log File Placement</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)