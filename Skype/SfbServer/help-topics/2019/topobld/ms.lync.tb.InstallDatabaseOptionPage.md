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
# <a name="install-database-options-page"></a>Страница параметров установки базы данных

Настраиваются расширенные параметры размещения баз данных и журнальных файлов в SQL Server. Доступны перечисленные ниже варианты.

> [!IMPORTANT]
> Выберите вариант, который наилучшим образом соответствует вашим требованиям и политикам, касающимся размещения данных и файлов журналов на SQL Server компьютерах.

 **Автоматически определите** расположение файлов базы данных. По умолчанию используется алгоритм, который определяет доступное пространство на SQL Server и распределяет файлы базы данных и журналов для оптимальной производительности.

 **Используйте SQL Server** по умолчанию: Выберите этот параметр для установки файлов баз данных и файлов журналов на основе параметров экземпляра в SQL Server. Эти параметры обычно настраиваются и управляются администратором баз данных.

 **Мы** эти пути на целевом SQL Server : Выберите этот параметр, чтобы определить собственные пути для SQL Server базы данных и журналов, введя полный путь к диску и папке, где будут размещены базы данных и файлы журналов.

> [!IMPORTANT]
> Вводимые пути могут быть изменены в соответствии с алгоритмами оптимизации производительности, действующими в установке. Дополнительные сведения см. в разделе [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **ОК**: нажмите кнопку "ОК", чтобы сохранить изменения.

 **Отмена**: нажмите кнопку "Отмена", чтобы отменить все изменения и вернуться на экран "Установка базы данных".

 **Справка**: нажмите кнопку "Справка" для перехода на страницу справки.

## <a name="see-also"></a>См. также

[Размещение данных и файла журнала SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)