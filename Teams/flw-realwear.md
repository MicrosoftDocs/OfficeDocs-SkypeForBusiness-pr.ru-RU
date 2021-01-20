---
title: Информация ИТ-администратора для клиента Microsoft Teams RealWear (предварительная версия)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Инструкции ИТ-администратора клиента Microsoft Teams для RealWear.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67f595e6b037eb6091d3b4e03e3258a13e12a4d1
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909393"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="94ff0-103">Microsoft Teams для RealWear</span><span class="sxs-lookup"><span data-stu-id="94ff0-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="94ff0-104">В этой статье рассказывается о клиенте Microsoft Teams для носимых головных устройств RealWear.</span><span class="sxs-lookup"><span data-stu-id="94ff0-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="94ff0-105">Сотрудники без компьютеров, использующие RealWear HMT-1 и HMT-1Z1, теперь могут взаимодействовать с удаленным экспертом, используя видеозвонки в Teams.</span><span class="sxs-lookup"><span data-stu-id="94ff0-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="94ff0-106">С помощью голосового интерфейса пользователя Teams для RealWear позволяют работникам на местах оставаться на 100% свободными от рук, сохраняя ситуационную осведомленность в шумной и опасной обстановке.</span><span class="sxs-lookup"><span data-stu-id="94ff0-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="94ff0-107">Показывая то, что они видят в режиме реального времени, полевые работники могут ускорить решение проблем и снизить риск дорогостоящих простоев.</span><span class="sxs-lookup"><span data-stu-id="94ff0-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="94ff0-108">Как развернуть Microsoft Teams для RealWear</span><span class="sxs-lookup"><span data-stu-id="94ff0-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="94ff0-109">Устройства RealWear обновлены до версии 11.2 или выше.</span><span class="sxs-lookup"><span data-stu-id="94ff0-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="94ff0-110">Дополнительные сведения см. [здесь](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="94ff0-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="94ff0-111">Доступ к [RealWear Foresight](https://cloud.realwear.com/) для распространения клиента Microsoft Teams для Realwear.</span><span class="sxs-lookup"><span data-stu-id="94ff0-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="94ff0-112">Требуемые лицензии</span><span class="sxs-lookup"><span data-stu-id="94ff0-112">Required Licenses</span></span>

<span data-ttu-id="94ff0-113">Лицензии Microsoft Teams являются частью подписок на Microsoft 365 и Office 365.</span><span class="sxs-lookup"><span data-stu-id="94ff0-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="94ff0-114">Никакого дополнительного лицензирования для использования Teams для RealWear не требуется.</span><span class="sxs-lookup"><span data-stu-id="94ff0-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="94ff0-115">Для получения дополнительной информации о получении команд ознакомьтесь с разделом  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="94ff0-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="94ff0-116">Управление устройствами RealWear</span><span class="sxs-lookup"><span data-stu-id="94ff0-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="94ff0-117">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="94ff0-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="94ff0-118">Устройствами RealWear можно управлять в режиме администратора устройств Android.</span><span class="sxs-lookup"><span data-stu-id="94ff0-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="94ff0-119">Поддержка управления через Android Enterprise ограничена, так как устройства в настоящее время не имеют мобильных сервисов Google (GMS).</span><span class="sxs-lookup"><span data-stu-id="94ff0-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="94ff0-120">Подробнее об управлении устройствами RealWear в Microsoft Endpoint Manager см. в разделе [Регистрация администраторов устройств Android в Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="94ff0-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="94ff0-121">Подробнее о политиках см. в статье [Как использовать Intune в среде без мобильных служб Google](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="94ff0-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="94ff0-122">Сторонние менеджеры по корпоративной мобильности (EMM)</span><span class="sxs-lookup"><span data-stu-id="94ff0-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="94ff0-123">Руководство по сторонним EMM см. в статье [Поддерживаемые поставщики корпоративных служб управления мобильностью](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="94ff0-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="94ff0-124">Содержимое для пользователей</span><span class="sxs-lookup"><span data-stu-id="94ff0-124">End-user content</span></span>

<span data-ttu-id="94ff0-125">Дополнительные сведения для конечных пользователей см. в статье [Использование Microsoft Teams для RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="94ff0-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
