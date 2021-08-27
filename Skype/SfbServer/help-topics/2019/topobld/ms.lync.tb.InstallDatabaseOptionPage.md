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
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: Настраиваются расширенные параметры размещения баз данных и журнальных файлов в SQL Server. Доступны перечисленные ниже варианты.
ms.openlocfilehash: 7a082bcace083a1b53ea5b94953a38364feb197a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611002"
---
# <a name="install-database-options-page"></a>Страница параметров установки базы данных

Настраиваются расширенные параметры размещения баз данных и журнальных файлов в SQL Server. Доступны перечисленные ниже варианты.

> [!IMPORTANT]
> Выберите параметр, который наилучшим образом соответствует вашим требованиям и политикам, касающимся размещения данных и файлов журналов на SQL Server компьютерах.

 **Автоматически определите** расположение файлов базы данных. По умолчанию используется алгоритм, который определяет доступное пространство на SQL Server и распределяет файлы базы данных и журналов для оптимальной производительности.

 **Используйте SQL Server** по умолчанию: выберите этот параметр для установки файлов баз данных и файлов журналов на основе параметров экземпляра в SQL Server. Эти параметры обычно настраиваются и управляются администратором баз данных.

 Мы эти пути на целевом **SQL Server**: Выберите этот параметр, чтобы определить собственные пути для SQL Server базы данных и журналов, введя полный путь к диску и папке, где будут размещены базы данных и файлы журналов.

> [!IMPORTANT]
> Вводимые пути могут быть изменены в соответствии с алгоритмами оптимизации производительности, действующими в установке. Дополнительные сведения см. в разделе [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell).

 **ОК**: нажмите кнопку "ОК", чтобы сохранить изменения.

 **Отмена**: нажмите кнопку "Отмена", чтобы отменить все изменения и вернуться на экран "Установка базы данных".

 **Справка**: нажмите кнопку "Справка" для перехода на страницу справки.

## <a name="see-also"></a>См. также

[Размещение данных и файла журнала SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)