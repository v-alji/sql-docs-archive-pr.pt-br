---
title: Executando operações de cópia em massa (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC]
- ODBC, bulk copy operations
- minimally logged operations [SQL Server Native Client]
- bulk copy [ODBC], about bulk copy
ms.assetid: 5c793405-487c-4f52-88b8-0091d529afb3
author: rothja
ms.author: jroth
ms.openlocfilehash: f2647ebca703eab46d7be0e1cfc2490a65384ee6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685109"
---
# <a name="performing-bulk-copy-operations-odbc"></a><span data-ttu-id="0a2aa-102">Executando operações de cópia em massa (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0a2aa-102">Performing Bulk Copy Operations (ODBC)</span></span>
  <span data-ttu-id="0a2aa-103">O padrão ODBC não dá suporte diretamente a operações de cópia em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a2aa-103">The ODBC standard does not directly support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="0a2aa-104">Quando conectado a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 7.0 ou posterior, o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte às funções DB-Library que executam operações de cópia em massa do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a2aa-104">When connected to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 or later, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports the DB-Library functions that perform [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy operations.</span></span> <span data-ttu-id="0a2aa-105">Esta extensão específica do driver fornece um caminho de atualização fácil para aplicativos DB-Library existente que usam funções de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-105">This driver-specific extension provides an easy upgrade path for existing DB-Library applications that use bulk copy functions.</span></span> <span data-ttu-id="0a2aa-106">O suporte especializado à cópia em massa se encontra nos seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="0a2aa-106">The specialized bulk copy support is in the following files:</span></span>  
  
-   <span data-ttu-id="0a2aa-107">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="0a2aa-107">sqlncli.h</span></span>  
  
     <span data-ttu-id="0a2aa-108">Inclui protótipos de função e definições de constantes para funções de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-108">Includes function prototypes and constant definitions for bulk copy functions.</span></span> <span data-ttu-id="0a2aa-109">O sqlncli.h deve ser incluído no aplicativo ODBC que executa operações de cópia em massa e deve estar no caminho de inclusão do aplicativo quando ele for compilado.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-109">sqlncli.h must be included in the ODBC application performing bulk copy operations and must be in the application's include path when it is compiled.</span></span>  
  
-   <span data-ttu-id="0a2aa-110">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="0a2aa-110">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="0a2aa-111">Deve estar no caminho da biblioteca do vinculador e ser especificado como um arquivo a ser vinculado.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-111">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="0a2aa-112">O sqlncli11.lib é distribuído com o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-112">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="0a2aa-113">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="0a2aa-113">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="0a2aa-114">Deve estar presente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-114">Must be present at execution time.</span></span> <span data-ttu-id="0a2aa-115">O sqlncli11.dll é distribuído com o driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-115">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a2aa-116">A função ODBC **SQLBulkOperations** não tem nenhuma relação com as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funções de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-116">The ODBC **SQLBulkOperations** function has no relationship to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk copy functions.</span></span> <span data-ttu-id="0a2aa-117">Os aplicativos devem usar as funções de cópia em massa específicas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para executar operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-117">Applications must use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific bulk-copy functions to perform bulk copy operations.</span></span>  
  
## <a name="minimally-logging-bulk-copies"></a><span data-ttu-id="0a2aa-118">Cópias em massa com registro mínimo</span><span class="sxs-lookup"><span data-stu-id="0a2aa-118">Minimally Logging Bulk Copies</span></span>  
 <span data-ttu-id="0a2aa-119">Com o modelo de Recuperação Completa, todas as operações de inserção de linha executadas pelo carregamento em massa são totalmente registradas no log de transações.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-119">With the Full Recovery model, all row-insert operations performed by bulk load are fully logged in the transaction log.</span></span> <span data-ttu-id="0a2aa-120">Em grandes carregamentos de dados, isso pode preencher o log de transações rapidamente.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-120">For large data loads, this can cause the transaction log to fill rapidly.</span></span> <span data-ttu-id="0a2aa-121">Em determinadas condições, é possível fazer um registro mínimo.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-121">Under certain conditions, minimally logging is possible.</span></span> <span data-ttu-id="0a2aa-122">O registro mínimo reduz a possibilidade de uma operação de carregamento em massa preencher o espaço do log, além de ser mais eficiente que o registro completo.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-122">Minimal logging reduces the possibility of a bulk load operation filling the log space and is also more efficient than full logging.</span></span>  
  
 <span data-ttu-id="0a2aa-123">Para obter informações sobre como usar o registro em log mínimo, consulte [pré-requisitos para log mínimo em importação em massa](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span><span class="sxs-lookup"><span data-stu-id="0a2aa-123">For information on using minimal logging, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a2aa-124">Comentários</span><span class="sxs-lookup"><span data-stu-id="0a2aa-124">Remarks</span></span>  
 <span data-ttu-id="0a2aa-125">Ao usar o bcp.exe no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou posterior, você pode obter erros em situações onde não havia erros antes do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a2aa-125">When using bcp.exe in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later, you might see errors in situations where there were no errors prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="0a2aa-126">Isto se deve ao fato de, nas versões posteriores, o bcp.exe não executar mais a conversão implícita de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-126">This is because in the later versions, bcp.exe no longer performs implicit data type conversion.</span></span> <span data-ttu-id="0a2aa-127">Antes do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], o bcp.exe convertia dados numéricos em um tipo de dados money, se a tabela de destino tivesse um tipo de dados money.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-127">Prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], bcp.exe converted numeric data to a money data type, if the target table had a money data type.</span></span> <span data-ttu-id="0a2aa-128">Porém, nessa situação, o bcp.exe simplesmente truncava os campos extras.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-128">However, in that situation, bcp.exe simply truncated extra fields.</span></span> <span data-ttu-id="0a2aa-129">A partir do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , se os tipos de dados não corresponderem entre o arquivo e a tabela de destino, bcp.exe gerará um erro se houver dados que teriam de ser truncados para se ajustarem à tabela de destino.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-129">Beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], if data types do not match between the file and the target table, bcp.exe will raise an error if there is any data that would have to be truncated to fit into the target table.</span></span> <span data-ttu-id="0a2aa-130">Para resolver este erro, corrija os dados para que correspondam ao tipo de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="0a2aa-130">To resolve this error, fix the data to match the target data type.</span></span> <span data-ttu-id="0a2aa-131">Opcionalmente, use o bcp.exe de uma versão anterior ao [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a2aa-131">Optionally, use bcp.exe from a release prior to [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a2aa-132">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0a2aa-132">In This Section</span></span>  
  
-   [<span data-ttu-id="0a2aa-133">Usando arquivos de dados e de formato</span><span class="sxs-lookup"><span data-stu-id="0a2aa-133">Using Data Files and Format Files</span></span>](using-data-files-and-format-files.md)  
  
-   [<span data-ttu-id="0a2aa-134">Cópia em massa de variáveis do programa</span><span class="sxs-lookup"><span data-stu-id="0a2aa-134">Bulk Copying from Program Variables</span></span>](bulk-copying-from-program-variables.md)  
  
-   [<span data-ttu-id="0a2aa-135">Gerenciando tamanhos de lote para cópia em massa</span><span class="sxs-lookup"><span data-stu-id="0a2aa-135">Managing Bulk Copy Batch Sizes</span></span>](managing-bulk-copy-batch-sizes.md)  
  
-   [<span data-ttu-id="0a2aa-136">Copiando em massa dados de texto e imagem</span><span class="sxs-lookup"><span data-stu-id="0a2aa-136">Bulk Copying Text and Image Data</span></span>](bulk-copying-text-and-image-data.md)  
  
-   [<span data-ttu-id="0a2aa-137">Convertendo de cópia em massa DB-Library em ODBC</span><span class="sxs-lookup"><span data-stu-id="0a2aa-137">Converting from DB-Library to ODBC Bulk Copy</span></span>](converting-from-db-library-to-odbc-bulk-copy.md)  
  
## <a name="see-also"></a><span data-ttu-id="0a2aa-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0a2aa-138">See Also</span></span>  
 <span data-ttu-id="0a2aa-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="0a2aa-139">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 [<span data-ttu-id="0a2aa-140">Importação e exportação em massa de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0a2aa-140">Bulk Import and Export of Data &#40;SQL Server&#41;</span></span>](../import-export/bulk-import-and-export-of-data-sql-server.md)  
  
  
