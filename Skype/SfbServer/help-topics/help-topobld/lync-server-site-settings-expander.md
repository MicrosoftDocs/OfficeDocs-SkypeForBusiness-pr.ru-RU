---
title: Расширитель параметров среды Lync Server
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
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Чтобы изменить свойства существующего сайта, выполните следующие действия:'
ms.openlocfilehash: 69555a04be4125e213ba2eca7afd7255100c0444
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217570"
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


