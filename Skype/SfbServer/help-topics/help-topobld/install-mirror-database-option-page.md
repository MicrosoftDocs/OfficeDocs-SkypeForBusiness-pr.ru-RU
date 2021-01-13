---
title: Страница параметров установки зеркальной базы данных
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
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: Параметры зеркальной базы данных определяются следующим образом.
ms.openlocfilehash: 63e3795cc52b9b8e3601b2260df253fdcd2d9c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806899"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="cc882-103">Страница параметров установки зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="cc882-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="cc882-104">**Параметры зеркальной базы данных** определяются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="cc882-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="cc882-105">Введите **путь к файловой** папке, чтобы определить расположение резервных SQL Server для зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc882-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cc882-106">Основной экземпляр SQL Server (именуемом или экземпляре по умолчанию) должен иметь разрешения на записи для файловой папки, определенной здесь.</span><span class="sxs-lookup"><span data-stu-id="cc882-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="cc882-107">Экземпляр зеркального SQL Server (именуемом или экземпляре по умолчанию) должен иметь разрешения на чтение для одной и той же файловой папки.</span><span class="sxs-lookup"><span data-stu-id="cc882-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
  <span data-ttu-id="cc882-108">При нажатии кнопки **ОК** выполняется принятие и сохранение изменений в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="cc882-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="cc882-109">При нажатии кнопки **Отмена** изменения отменяются, а диалоговое окно закрывается.</span><span class="sxs-lookup"><span data-stu-id="cc882-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="cc882-110">При нажатии кнопки **Справка** отображается данный экран справки.</span><span class="sxs-lookup"><span data-stu-id="cc882-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc882-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cc882-111">See also</span></span>

[<span data-ttu-id="cc882-112">Развертывание SQL зеркального отражания для высокой доступности серверов в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="cc882-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server 2015</span></span>](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
