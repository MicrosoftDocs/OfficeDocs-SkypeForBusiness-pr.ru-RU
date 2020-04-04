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
ms.openlocfilehash: ee23b25f377770457c597e09d2e570a23e7e90da
ms.sourcegitcommit: 482050a77a85aeb8dae52f86c9344023487e1b70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "43113202"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="20be8-103">Microsoft Teams для RealWear</span><span class="sxs-lookup"><span data-stu-id="20be8-103">Microsoft Teams for RealWear</span></span>

> [!NOTE]
> <span data-ttu-id="20be8-104">Это функция для предварительного или раннего доступа.</span><span class="sxs-lookup"><span data-stu-id="20be8-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="20be8-105">В этой статье рассказывается о клиенте Microsoft Teams для носимых головных устройств RealWear.</span><span class="sxs-lookup"><span data-stu-id="20be8-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="20be8-106">Работники FirstLine, использующие RealWear HMT-1 и HMT-1Z1, теперь могут сотрудничать с удаленным экспертом, используя видеосвязь в Teams.</span><span class="sxs-lookup"><span data-stu-id="20be8-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="20be8-107">С помощью голосового интерфейса пользователя Teams для RealWear позволяют работникам на местах оставаться на 100% свободными от рук, сохраняя ситуационную осведомленность в шумной и опасной обстановке.</span><span class="sxs-lookup"><span data-stu-id="20be8-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="20be8-108">Показывая то, что они видят в режиме реального времени, полевые работники могут ускорить решение проблем и снизить риск дорогостоящих простоев.</span><span class="sxs-lookup"><span data-stu-id="20be8-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="20be8-109">Как развернуть Microsoft Teams для RealWear</span><span class="sxs-lookup"><span data-stu-id="20be8-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="20be8-110">Клиент Microsoft Teams для RealWear в настоящее время находится в открытом предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="20be8-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="20be8-111">Для участия в этом предварительном просмотре вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="20be8-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="20be8-112">Устройства RealWear обновлены до версии 10.5.0 или выше.</span><span class="sxs-lookup"><span data-stu-id="20be8-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="20be8-113">Больше информации [здесь](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="20be8-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20be8-114">Зарегистрируйтесь [здесь](https://www.realwear.com/solutions/microsoft-teams/#C1) для доступа в клиента Teams для RealWear в [RealWear Foresight](https://cloud.realwear.com/).</span><span class="sxs-lookup"><span data-stu-id="20be8-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="20be8-115">Требуемые лицензии</span><span class="sxs-lookup"><span data-stu-id="20be8-115">Required Licenses</span></span>

<span data-ttu-id="20be8-116">Лицензии Microsoft Teams являются частью подписок на Office 365.</span><span class="sxs-lookup"><span data-stu-id="20be8-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="20be8-117">Никакого дополнительного лицензирования для использования Teams для RealWear не требуется.</span><span class="sxs-lookup"><span data-stu-id="20be8-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="20be8-118">Для получения дополнительной информации о получении команд ознакомьтесь с разделом  [Как получить доступ к Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="20be8-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="20be8-119">Управление устройствами RealWear</span><span class="sxs-lookup"><span data-stu-id="20be8-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="20be8-120">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="20be8-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="20be8-121">Устройствами RealWear можно управлять в режиме администратора устройств Android.</span><span class="sxs-lookup"><span data-stu-id="20be8-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="20be8-122">Поддержка управления через Android Enterprise ограничена, так как устройства в настоящее время не имеют мобильных сервисов Google (GMS).</span><span class="sxs-lookup"><span data-stu-id="20be8-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="20be8-123">Подробнее об управлении устройствами RealWear в Microsoft Endpoint Manager см. в разделе [Регистрация администраторов устройств Android в Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="20be8-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="20be8-124">Сторонние менеджеры по корпоративной мобильности (EMM)</span><span class="sxs-lookup"><span data-stu-id="20be8-124">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="20be8-125">Руководство по сторонним EMM см. в статье [Поддерживаемые поставщики корпоративных служб управления мобильностью](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="20be8-125">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="20be8-126">Содержимое для пользователей</span><span class="sxs-lookup"><span data-stu-id="20be8-126">End-user content</span></span>

<span data-ttu-id="20be8-127">Дополнительные сведения для конечных пользователей см. в статье [Использование Microsoft Teams для RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="20be8-127">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
