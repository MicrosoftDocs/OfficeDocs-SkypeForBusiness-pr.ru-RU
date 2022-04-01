---
title: Новые возможности прямой маршрутии
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: В этой статье описаны новые возможности прямой маршрутии. Проверяйте их по-разму, чтобы проверить, нет ли обновлений.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584334"
---
# <a name="whats-new-for-direct-routing"></a>Новые возможности прямой маршрутии

В этой статье описаны новые возможности прямой маршрутии. Проверяйте их по-разму, чтобы проверить, нет ли обновлений.

## <a name="sip-support"></a>Поддержка SIP

1 июня 2022 г. корпорация Майкрософт удалит поддержку sip-all.pstnhub.microsoft.com и sip-all.pstnhub.gov.teams.microsoft.us FQDNs из прямой маршрутии.

Если до 1 июня не будут предприняты какие-либо действия, пользователи не смогут звонить и принимать звонки с помощью прямой маршрутии.

Чтобы предотвратить влияние службы:

- Для классификации или правил ACL используйте рекомендуемые подсети: (52.112.0.0/14 и 52.120.0.0/14).
- Не используйте FQDN sip-all при настройке элементов управления границами сеанса для прямой маршрутии.

Дополнительные сведения см. в [этой ссылке](direct-routing-plan.md).

## <a name="tls-certificates"></a>Сертификаты TLS

Microsoft 365 обновляет Teams и другие службы, чтобы использовать другой набор корневых сертификатов.

Дополнительные сведения и полный список затронутых служб см. в этой Microsoft 365 служб, включая [Microsoft Teams.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676)

## <a name="certificate-authorities"></a>Органы сертификации

С 1 февраля 2022 г. интерфейс SIP прямой маршрутии будет доверять только сертификатам, подписанным центром сертификации (ЦС), которые являются частью программы доверенных корневых сертификатов Майкрософт. Чтобы избежать влияния на службу, сэкономим на следующих действиях:

- Убедитесь, что сертификат SBC подписан ЦС, который является частью программы доверенных корневых сертификатов Майкрософт.
- Убедитесь, что расширение для расширенного использования ключа (EKU) сертификата включает в себя "Проверка подлинности сервера".

Дополнительные сведения о программе доверенных корневых сертификатов Майкрософт см. в этой [теме](/security/trusted-root/program-requirements).

Список надежных ЦС см. в списке [сертификатов, включаемом в список ЦС Майкрософт](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Замена headers

Начиная с апреля 2022 г. прямая маршрутия отклоняет запросы SIP с задаваемой заменой. Потоки, в которые Корпорация Майкрософт отправляет заглавную запись Replaces на контроллер границы сеанса(SBC), не меняются.

Проверьте конфигурации SBC и убедитесь, что вы не используете заменять заглавные в запросах SIP.

## <a name="tls10-and-11"></a>TLS1.0 и 1.1

Чтобы обеспечить наилучшее шифрование в классе, корпорация Майкрософт планирует депрецировать TLS-версии 1.0 и 1.1. 3 апреля 2022 г. корпорация Майкрософт привячит к использованию TLS1.2 для интерфейса SIP прямой маршрутии.

Чтобы избежать влияния на службу, убедитесь, что ваши SBCs настроены для поддержки TLS1.2 и могут подключаться с помощью одного из следующих наборов шифров:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 т. е. ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 т. е. ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 т. е. ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 т. е. ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Статьи по теме

- [Прямая маршрутия — протокол SIP](direct-routing-protocols-sip.md)
