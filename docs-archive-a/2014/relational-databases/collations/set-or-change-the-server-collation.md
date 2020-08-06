---
title: Definir ou alterar a ordenação do servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- server collations [SQL Server]
- collations [SQL Server], server
ms.assetid: 3242deef-6f5f-4051-a121-36b3b4da851d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35e7be051c8cf63a272f2bf42fb54b1c45ed4160
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583639"
---
# <a name="set-or-change-the-server-collation"></a><span data-ttu-id="07792-102">Definir ou alterar a ordenação do servidor</span><span class="sxs-lookup"><span data-stu-id="07792-102">Set or Change the Server Collation</span></span>
  <span data-ttu-id="07792-103">A ordenação do servidor atua como a ordenação padrão de todos os bancos de dados do sistema instalados com a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], e também com quaisquer bancos de dados de usuário recém-criados.</span><span class="sxs-lookup"><span data-stu-id="07792-103">The server collation acts as the default collation for all system databases that are installed with the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and also any newly created user databases.</span></span> <span data-ttu-id="07792-104">A ordenação do servidor é especificada durante a instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07792-104">The server collation is specified during [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="07792-105">Para obter mais informações, consulte [Suporte a ordenações e a Unicode](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="07792-105">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
## <a name="changing-the-server-collation"></a><span data-ttu-id="07792-106">Alterando a ordenação do servidor</span><span class="sxs-lookup"><span data-stu-id="07792-106">Changing the Server Collation</span></span>  
 <span data-ttu-id="07792-107">A alteração da ordenação padrão para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ser uma operação complexa e engloba as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="07792-107">Changing the default collation for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be a complex operation and involves the following steps:</span></span>  
  
-   <span data-ttu-id="07792-108">Verifique se você tem todas as informações ou scripts necessários para recriar seus bancos de dados de usuário e todos os objetos neles.</span><span class="sxs-lookup"><span data-stu-id="07792-108">Make sure you have all the information or scripts needed to re-create your user databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="07792-109">Exporte todos os seus dados usando uma ferramenta como [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="07792-109">Export all your data using a tool such as the [bcp Utility](../../tools/bcp-utility.md).</span></span> <span data-ttu-id="07792-110">Para obter mais informações, consulte [Importação e exportação em massa de dados &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="07792-110">For more information, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="07792-111">Descarte todos os bancos de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="07792-111">Drop all the user databases.</span></span>  
  
-   <span data-ttu-id="07792-112">Reconstrua o banco de dados mestre especificando a nova ordenação na propriedade SQLCOLLATION do comando **setup** .</span><span class="sxs-lookup"><span data-stu-id="07792-112">Rebuild the master database specifying the new collation in the SQLCOLLATION property of the **setup** command.</span></span> <span data-ttu-id="07792-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="07792-113">For example:</span></span>  
  
    ```  
    Setup /QUIET /ACTION=REBUILDDATABASE /INSTANCENAME=InstanceName   
    /SQLSYSADMINACCOUNTS=accounts /[ SAPWD= StrongPassword ]   
    /SQLCOLLATION=CollationName  
    ```  
  
     <span data-ttu-id="07792-114">Para obter mais informações, consulte [Recriar bancos de dados do sistema](../databases/system-databases.md).</span><span class="sxs-lookup"><span data-stu-id="07792-114">For more information, see [Rebuild System Databases](../databases/system-databases.md).</span></span>  
  
-   <span data-ttu-id="07792-115">Crie todos os bancos de dados e todos os objetos neles.</span><span class="sxs-lookup"><span data-stu-id="07792-115">Create all the databases and all the objects in them.</span></span>  
  
-   <span data-ttu-id="07792-116">Importe todos os dados.</span><span class="sxs-lookup"><span data-stu-id="07792-116">Import all your data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07792-117">Em vez de alterar a ordenação padrão de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode especificar uma ordenação para cada novo banco de dados que criar.</span><span class="sxs-lookup"><span data-stu-id="07792-117">Instead of changing the default collation of an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can specify a default collation for each new database you create.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07792-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07792-118">See Also</span></span>  
 <span data-ttu-id="07792-119">[Suporte a ordenações e a Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="07792-119">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="07792-120">[Definir ou alterar a ordenação de banco de dados](set-or-change-the-database-collation.md) </span><span class="sxs-lookup"><span data-stu-id="07792-120">[Set or Change the Database Collation](set-or-change-the-database-collation.md) </span></span>  
 <span data-ttu-id="07792-121">[Definir ou alterar a ordenação de coluna](set-or-change-the-column-collation.md) </span><span class="sxs-lookup"><span data-stu-id="07792-121">[Set or Change the Column Collation](set-or-change-the-column-collation.md) </span></span>  
 [<span data-ttu-id="07792-122">Recompilar bancos de dados do sistema</span><span class="sxs-lookup"><span data-stu-id="07792-122">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
