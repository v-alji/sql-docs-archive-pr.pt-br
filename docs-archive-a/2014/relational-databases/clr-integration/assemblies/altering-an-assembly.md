---
title: Alterando um assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration], modifying
- permissions [CLR integration]
- altering assemblies
- ALTER ASSEMBLY statement
ms.assetid: 9e765fbd-f339-473c-8537-22f478e79696
author: rothja
ms.author: jroth
ms.openlocfilehash: c22ca979675d3b7f263e3bc6de0c41c134a1abcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87682286"
---
# <a name="altering-an-assembly"></a><span data-ttu-id="d4d29-102">Alterando um assembly</span><span class="sxs-lookup"><span data-stu-id="d4d29-102">Altering an Assembly</span></span>
  <span data-ttu-id="d4d29-103">Os assemblies que foram registrados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] podem ser atualizados de uma versão mais recente que use a instrução ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d4d29-103">Assemblies that have been registered in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can be updated from a more recent version using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="d4d29-104">Para atualizar um assembly, use a instrução ALTER ASSEMBLY com a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="d4d29-104">To update an assembly, use the ALTER ASSEMBLY statement with the following syntax:</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
```  
  
 <span data-ttu-id="d4d29-105">A instrução ALTER ASSEMBLY não interrompe processos em execução que estejam usando o assembly; os processos continuam executando com o assembly inalterado.</span><span class="sxs-lookup"><span data-stu-id="d4d29-105">ALTER ASSEMBLY does not disrupt currently running processes that are using the assembly; the processes continue executing with the unaltered assembly.</span></span> <span data-ttu-id="d4d29-106">ALTER ASSEMBLY não pode ser usada para alterar as assinaturas de funções CLR (Common Language Runtime), funções de agregação, procedimentos armazenados e gatilhos.</span><span class="sxs-lookup"><span data-stu-id="d4d29-106">ALTER ASSEMBLY cannot be used to change the signatures of common language runtime (CLR) functions, aggregate functions, stored procedures, and triggers.</span></span> <span data-ttu-id="d4d29-107">Novos métodos públicos podem ser adicionados ao assembly, métodos particulares podem ser modificados de alguma forma e métodos públicos podem ser modificados enquanto assinaturas ou atributos não são alterados.</span><span class="sxs-lookup"><span data-stu-id="d4d29-107">New public methods can be added to the assembly, private methods can be modified in any way, and public methods can be modified as long as signatures or attributes are not changed.</span></span> <span data-ttu-id="d4d29-108">Os campos contidos em um tipo definido pelo usuário serializado nativo, incluindo membros de dados ou classes base, não podem ser alterados com o uso de ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d4d29-108">Fields that are contained within a native-serialized user-defined type, including data members or base classes, cannot be changed by using ALTER ASSEMBLY.</span></span> <span data-ttu-id="d4d29-109">Não é oferecido suporte a todas as demais alterações.</span><span class="sxs-lookup"><span data-stu-id="d4d29-109">All other changes are unsupported.</span></span> <span data-ttu-id="d4d29-110">Para obter mais informações, consulte [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d4d29-110">For more information, see [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
## <a name="changing-the-permission-set-of-an-assembly"></a><span data-ttu-id="d4d29-111">Alterando o conjunto de permissões de um assembly</span><span class="sxs-lookup"><span data-stu-id="d4d29-111">Changing the Permission Set of an Assembly</span></span>  
 <span data-ttu-id="d4d29-112">O conjunto de permissões de um assembly pode também ser alterado com a instrução ALTER ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d4d29-112">The permission set of an assembly can also be changed using the ALTER ASSEMBLY statement.</span></span> <span data-ttu-id="d4d29-113">A instrução a seguir altera o conjunto de permissões do assembly SQLCLRTest para `EXTERNAL_ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="d4d29-113">The following statement changes the permission set of the SQLCLRTest assembly to `EXTERNAL_ACCESS`.</span></span>  
  
```  
ALTER ASSEMBLY SQLCLRTest  
WITH PERMISSION_SET = EXTERNAL_ACCESS   
```  
  
 <span data-ttu-id="d4d29-114">Se o conjunto de permissões de um assembly estiver sendo alterado de `SAFE` para `EXTERNAL_ACCESS` ou `UNSAFE`, uma chave assimétrica e o logon correspondente com a permissão `EXTERNAL ACCESS ASSEMBLY` ou a permissão `UNSAFE ASSEMBLY` do assembly deverão ser criados primeiro.</span><span class="sxs-lookup"><span data-stu-id="d4d29-114">If the permission set of an assembly is being changed from `SAFE` to `EXTERNAL_ACCESS` or `UNSAFE`, an asymmetric key and corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission or `UNSAFE ASSEMBLY` permission for the assembly must first be created.</span></span> <span data-ttu-id="d4d29-115">Para obter mais informações, consulte [Criando um assembly](creating-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="d4d29-115">For more information, see [Creating an Assembly](creating-an-assembly.md).</span></span>  
  
## <a name="adding-the-source-code-of-an-assembly"></a><span data-ttu-id="d4d29-116">Adicionando o código-fonte de um assembly</span><span class="sxs-lookup"><span data-stu-id="d4d29-116">Adding the Source Code of an Assembly</span></span>  
 <span data-ttu-id="d4d29-117">A cláusula ADD FILE na sintaxe ALTER ASSEMBLY não está presente em CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="d4d29-117">The ADD FILE clause in the ALTER ASSEMBLY syntax is not present in CREATE ASSEMBLY.</span></span> <span data-ttu-id="d4d29-118">Você pode usá-la para adicionar código-fonte ou outros arquivos associados a um assembly.</span><span class="sxs-lookup"><span data-stu-id="d4d29-118">You can use it to add source code or any other files associated with an assembly.</span></span> <span data-ttu-id="d4d29-119">Os arquivos serão copiados dos seus locais originais e armazenados em tabelas do sistema do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d4d29-119">The files are copied from their original locations and stored in system tables in the database.</span></span> <span data-ttu-id="d4d29-120">Isso garante que você sempre tenha código-fonte ou outros arquivos à mão, se precisar recriar ou documentar a versão atual do UDT.</span><span class="sxs-lookup"><span data-stu-id="d4d29-120">This ensures that you always have source code or other files on hand should you ever need to re-create or document the current version of the UDT.</span></span>  
  
 <span data-ttu-id="d4d29-121">A instrução a seguir adiciona o código-fonte de classe Point.cs para o UDT Point.</span><span class="sxs-lookup"><span data-stu-id="d4d29-121">The following statement adds the Point.cs class source code for the Point UDT.</span></span> <span data-ttu-id="d4d29-122">O texto contendo o arquivo Point.cs será copiado e armazenado no banco de dados com o nome "PointSource".</span><span class="sxs-lookup"><span data-stu-id="d4d29-122">This copies the text contained in the Point.cs file and stores it in the database under the name "PointSource".</span></span>  
  
 `ALTER ASSEMBLY Point`  
  
 `ADD FILE FROM 'C:\Projects\Point\Point.cs' AS PointSource`  
  
## <a name="see-also"></a><span data-ttu-id="d4d29-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d4d29-123">See Also</span></span>  
 <span data-ttu-id="d4d29-124">[Gerenciando assemblies de integração CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="d4d29-124">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="d4d29-125">[Criando um assembly](creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="d4d29-125">[Creating an Assembly](creating-an-assembly.md) </span></span>  
 <span data-ttu-id="d4d29-126">[Descartando um assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="d4d29-126">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 [<span data-ttu-id="d4d29-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d4d29-127">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
  
