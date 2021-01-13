---
title: Расширитель параметров среды Lync Server
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
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Чтобы изменить свойства существующего сайта, выполните следующие действия:'
ms.openlocfilehash: acfd7e312dbde97e847a9b97d9730a6d0b3488da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832919"
---
# <a name="lync-server-site-settings-expander"></a>Расширитель параметров среды Lync Server

Чтобы изменить свойства существующего сайта, выполните следующие действия:



## <a name="site-properties"></a>Свойства сайта

В свойствах сайта можно изменить имя (обязательный параметр), описание (необязательный параметр), город (необязательный параметр), область и регион (необязательный параметр), а также код страны или региона (необязательный параметр).

Дополнительные сведения о свойствах сайта см. в разделе [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).

## <a name="federation-route-properties"></a>Свойства маршрута федерации

Чтобы задать назначение маршрута федерации для сайта, сначала следует включить федерацию на пограничном сервере или в пуле пограничных серверов. Если федерация на пограничном сервере или в пуле не включена, параметры назначения маршрута федерации для сайта будут недоступны для изменения.

Если на пограничном сервере или в пуле настроена федерация, выберите **Включить** на уровне сайтов. После этого выберите пограничный сервер или Директор в раскрывающемся списке, чтобы задать его в качестве маршрута федерации.

> [!CAUTION]
> Этот параметр охватывает все сайты. Убедитесь, что настройка данного сайта подходит для всех остальных сайтов.

## <a name="see-also"></a>См. также

Дополнительные сведения см. в разделе [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).


