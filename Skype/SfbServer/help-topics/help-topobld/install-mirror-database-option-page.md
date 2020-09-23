---
title: Страница параметров установки зеркальной базы данных
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
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: Параметры зеркальной базы данных определяются следующим образом.
ms.openlocfilehash: d522cc62f02d9021eaf6267db0b93aa4d42d3a3d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215330"
---
# <a name="install-mirror-database-option-page"></a>Страница параметров установки зеркальной базы данных
 
**Параметры зеркальной базы данных** определяются следующим образом.
  
- Введите **путь к общему файловому ресурсу** , чтобы определить расположение резервных файлов SQL Server для зеркальной базы данных.
    
    > [!NOTE]
    > Основной экземпляр SQL Server (как именованный экземпляр, так и экземпляр по умолчанию) должен иметь разрешения на запись в общую папку, которую вы определили здесь. Зеркальный экземпляр SQL Server (как именованный экземпляр, так и экземпляр по умолчанию) должен иметь разрешения на чтение того же общего файлового ресурса. 
  
  При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.
  
  При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.
  
  При нажатии кнопки **Справка** отображается данный экран справки.
  
## <a name="see-also"></a>См. также

[Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Skype для бизнеса Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
