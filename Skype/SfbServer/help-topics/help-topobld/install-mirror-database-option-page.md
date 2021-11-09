---
title: Страница параметров установки зеркальной базы данных
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: Параметры зеркальной базы данных определяются следующим образом.
ms.openlocfilehash: 2869af0b7ca4d455fc2fe1aea973e8764cbe0be7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847712"
---
# <a name="install-mirror-database-option-page"></a>Страница параметров установки зеркальной базы данных
 
**Параметры зеркальной базы данных** определяются следующим образом.
  
- Введите **путь к файлу,** чтобы определить расположение резервного SQL Server для зеркального копирования базы данных.
    
    > [!NOTE]
    > У основного SQL Server (либо имени экземпляра, либо экземпляра по умолчанию) должны быть разрешения на записи в определенный здесь файл. Экземпляр зеркального SQL Server (или названный экземпляр или экземпляр по умолчанию) должен иметь разрешения на чтение одной и той же папки файла. 
  
  При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.
  
  При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.
  
  При нажатии кнопки **Справка** отображается данный экран справки.
  
## <a name="see-also"></a>См. также

[Развертывание SQL для высокой доступности back End Server в Skype для бизнеса Server 2015 г.](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
