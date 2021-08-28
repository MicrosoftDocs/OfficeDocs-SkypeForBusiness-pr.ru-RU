---
title: Создание карты здания для панели мониторинга качества звонка (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Узнайте, как создать карту здания, которую можно использовать для отправки данных о клиенте и здании на панели мониторинга качества звонка (CQD).
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634103"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Создание карты здания для панели мониторинга качества звонка (CQD)

В развертывании Microsoft Teams или Skype для бизнеса Online все клиенты являются внешними. В результате по умолчанию на панели мониторинга качества звонка (CQD) все клиенты сообщаются как внешние независимо от того, подключен ли клиент к внутренней корпоративной сети.

При работе с CQD необходимо знать расположение конечной точки и ее подключение к сети, которую вы можете управлять, или сеть, которую вы не можете управлять, предполагая, что вы можете улучшить только те сети, которые вы можете управлять. Выкладывая сведения о подсети и здания в CQD, вы включаете CQD, чтобы определить, подключена ли конечная точка к внутренней (управляемой) или внешней (неуправляемой) сети. Поэтому очень важно создать карту здания для организации и добавить ее в [CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Средства сопоставления зданий

Существует множество способов соотоставить подсети организации. Если вам нужна помощь, воспользуйтесь модулем PowerShell CQDTools, описанным в этой [записи блога.](https://aka.ms/cqdtools) Эти средства основаны на PowerShell и используют сайты и службы Active Directory (AD) и службы DHCP Майкрософт для предварительного заполнения файла здания. Эти средства помогут вам в следующих задачах:

1. Запрос сайтов и служб AD и создание файла здания на основе содержащихся в них сведений.
1. Запросите сервер или сервер Microsoft DHCP, чтобы получить сведения о подсети и автоматически создать файл здания.
1. Проверка существующего файла здания, проверка на совпадения и повторы.
1. Поиск неподтверщенных подсетей в CQD.

## <a name="related-topics"></a>Статьи по теме

[Upload клиента и здания в CQD](CQD-upload-tenant-building-data.md)