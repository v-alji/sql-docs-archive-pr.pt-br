---
title: Selecionar dispositivo de backup | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683560"
---
# <a name="select-backup-device"></a><span data-ttu-id="44e70-102">Selecionar Dispositivo de Backup</span><span class="sxs-lookup"><span data-stu-id="44e70-102">Select Backup Device</span></span>
  <span data-ttu-id="44e70-103">Use a caixa de diálogo **Selecionar Dispositivo de Backup** para selecionar um dispositivo lógico de backup para a operação de restauração.</span><span class="sxs-lookup"><span data-stu-id="44e70-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="44e70-104">O dispositivo lógico de backup é definido pelo usuário e correspondente a um dispositivo físico, que pode ser uma unidade de fita ou de disco fornecidas pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="44e70-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="44e70-105">Para que um backup possa utilizar vários dispositivos de backup, todos precisam corresponder a um único tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44e70-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="44e70-106">**Para usar o SQL Server Management Studio para exibir o conteúdo de um dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="44e70-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="44e70-107">Exibir o conteúdo de um arquivo ou fita de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44e70-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="44e70-108">Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44e70-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="44e70-109">Opções</span><span class="sxs-lookup"><span data-stu-id="44e70-109">Options</span></span>  
 <span data-ttu-id="44e70-110">**Dispositivo de backup**</span><span class="sxs-lookup"><span data-stu-id="44e70-110">**Backup device**</span></span>  
 <span data-ttu-id="44e70-111">Na caixa de listagem, selecione o nome de um dispositivo lógico de backup do qual você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="44e70-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="44e70-112">Para obter informações sobre como exibir o conteúdo de um dispositivo de backup, veja [Exibir as propriedades e o conteúdo de um dispositivo de backup lógico &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="44e70-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44e70-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="44e70-113">Remarks</span></span>  
 <span data-ttu-id="44e70-114">Caso não se observe um dispositivo lógico de backup que contenha um backup procurado na lista, isso indica que o backup pode ter sido gravado diretamente em um ou mais arquivos ou unidades de fita.</span><span class="sxs-lookup"><span data-stu-id="44e70-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="44e70-115">Nesse caso, cancele a caixa de diálogo **Selecionar Dispositivo de Backup** . Na caixa de diálogo **Especificar Backup** , selecione **Arquivo** ou **Fita** na caixa de listagem **Mídia do backup** .</span><span class="sxs-lookup"><span data-stu-id="44e70-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e70-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="44e70-116">See Also</span></span>  
 [<span data-ttu-id="44e70-117">Dispositivos de backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="44e70-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
