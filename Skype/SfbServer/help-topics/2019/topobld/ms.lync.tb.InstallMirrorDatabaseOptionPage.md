---
title: Установка страница параметров зеркальной базы данных
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 'Настройте параметры зеркальной базы данных определяются следующим:'
ms.openlocfilehash: 2cd793883baf5e5d567e9248e60f6601f8e1aa96
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "19989764"
---
# <a name="install-mirror-database-option-page"></a><span data-ttu-id="c4865-103">Установка страница параметров зеркальной базы данных</span><span class="sxs-lookup"><span data-stu-id="c4865-103">Install Mirror Database Option Page</span></span>
 
<span data-ttu-id="c4865-104">Настройте **Параметры зеркальной базы данных** определяются следующим:</span><span class="sxs-lookup"><span data-stu-id="c4865-104">You configure **Mirror Database Settings** by defining the following:</span></span>
  
- <span data-ttu-id="c4865-105">Введите **путь к файлу совместно использовать** для определения местоположения файлов резервных копий SQL Server для зеркалируемой базы данных.</span><span class="sxs-lookup"><span data-stu-id="c4865-105">Type the **Path to file share** to define the location for the backup SQL Server files for the database being mirrored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4865-106">Основной экземпляр SQL Server (именованный экземпляр или экземпляр по умолчанию) необходимо иметь разрешения на запись в общую папку файлов, здесь.</span><span class="sxs-lookup"><span data-stu-id="c4865-106">The primary SQL Server instance (either named instance or default instance) must have write permissions to the file share you define here.</span></span> <span data-ttu-id="c4865-107">Зеркальный экземпляр SQL Server (именованный экземпляр или экземпляр по умолчанию) необходимо иметь разрешения на чтение же общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="c4865-107">The mirror SQL Server instance (either named instance or default instance) must have read permissions to the same file share.</span></span> 
  
 <span data-ttu-id="c4865-108">**ОК**. Принятие и фиксация изменений, внесенных в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="c4865-108">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="c4865-109">**Отмена**. Отмена изменений и закрытие диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="c4865-109">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="c4865-110">**Справка**. Отображение этого экрана справки.</span><span class="sxs-lookup"><span data-stu-id="c4865-110">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4865-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c4865-111">See also</span></span>

[<span data-ttu-id="c4865-112">Развертывание зеркального отображения SQL для обеспечения высокой доступности Тыловой сервер в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c4865-112">Deploy SQL mirroring for Back End Server high availability in Skype for Business Server</span></span>](../../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)