---
title: Добавление параметров пограничных серверов для Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: Вы определяете новый пул Edge Server или Edge и имеете возможность определить возможности для нового сервера или пула. Доступные для выбора параметры приведены ниже.
ms.openlocfilehash: 0c02e03a1e0e1a8c8455be48915f1c488f4d021f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845542"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Добавление параметров пограничных серверов для Lync Server 2010

Вы определяете новый пул Edge Server или Edge и имеете возможность определить возможности для нового сервера или пула. Доступные для выбора параметры приведены ниже.

- **Использовать единое полное доменное имя и IP-адрес**. Установите этот флажок, чтобы использовать один адрес IPv4 или IPv6 (если выбрано использование и IPv4, и IPv6, то необходимо определить каждый из этих типов адресов) и одно полное доменное имя для внешних интерфейсов пограничного сервера.

    > [!IMPORTANT]
    > Если выбрать этот параметр, будет использован только один IP-адрес (или один адрес IPv4 и один адрес IPv6), однако необходимо назначить разные порты для каждого интерфейса пограничного сервера.

- **Включить федерацию (порт 5061)**. Установите этот флажок, если необходимо установить федерацию с другими федерациями, поставщиками или узлами SIP.

- Внешний IP-адрес этого пула **Edge** переведен nat : Выберите этот контрольный ящик, если вы используете частные IP-адреса для внешних интерфейсов Edge и предоставит устройство для перевода сетевых адресов (NAT), чтобы логически разместить пул Edge Server или Edge.

## <a name="see-also"></a>См. также

[Планирование доступа внешних пользователей](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[Развертывание доступа внешних пользователей](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)