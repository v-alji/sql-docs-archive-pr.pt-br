---
title: Colocar arquivos de dados e de log em unidades separadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575772"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="20cad-102">Colocar arquivos de dados e de log em unidades separadas</span><span class="sxs-lookup"><span data-stu-id="20cad-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="20cad-103">Esta regra verifica se os arquivos de dados e de log são colocados em unidades lógicas separadas.</span><span class="sxs-lookup"><span data-stu-id="20cad-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="20cad-104">Colocar arquivos de dados e de log no mesmo dispositivo pode causar contenção para esse dispositivo e resultar em um baixo desempenho.</span><span class="sxs-lookup"><span data-stu-id="20cad-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="20cad-105">Colocar os arquivos em unidades separadas permite que a atividade de E/S ocorra ao mesmo tempo para os arquivos de dados e de log.</span><span class="sxs-lookup"><span data-stu-id="20cad-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="20cad-106">Práticas Recomendadas</span><span class="sxs-lookup"><span data-stu-id="20cad-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="20cad-107">Ao criar um banco de dados novo, especifique unidades separadas para os dados e o log.</span><span class="sxs-lookup"><span data-stu-id="20cad-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="20cad-108">Para mover os arquivos depois que o banco de dados é criado, o banco de dados deve ser usado offline.</span><span class="sxs-lookup"><span data-stu-id="20cad-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="20cad-109">Mova os arquivos usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="20cad-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20cad-110">Essa política não pode detectar dispositivos físicos separados por pontos de montagem</span><span class="sxs-lookup"><span data-stu-id="20cad-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="20cad-111">Restaure o banco de dados do backup usando a instrução RESTORE DATABASE com a opção WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="20cad-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="20cad-112">Desanexe e, em seguida, anexe o banco de dados especificando locais separados para os dispositivos de dados e de log.</span><span class="sxs-lookup"><span data-stu-id="20cad-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="20cad-113">Especifique um novo local executando a instrução ALTER DATABASE com a opção MODIFY FILE e, em seguida, reinicie a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20cad-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="20cad-114">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="20cad-114">For More Information</span></span>  
 [<span data-ttu-id="20cad-115">Mover arquivos de banco de dados</span><span class="sxs-lookup"><span data-stu-id="20cad-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="20cad-116">Mover bancos de dados de usuário</span><span class="sxs-lookup"><span data-stu-id="20cad-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="20cad-117">Anexar e desanexar bancos de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="20cad-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="20cad-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="20cad-118">See Also</span></span>  
 [<span data-ttu-id="20cad-119">Monitorar e impor melhores práticas usando o gerenciamento baseado em políticas</span><span class="sxs-lookup"><span data-stu-id="20cad-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
