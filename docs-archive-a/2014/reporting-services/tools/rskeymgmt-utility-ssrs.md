---
title: Utilitário rskeymgmt (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], encryption
- joining report server instances [SQL Server]
- report server scale-out deployments [Reporting Services]
- cryptography [Reporting Services]
- multiple report server instances
- command prompt utilities [Reporting Services]
- report servers [Reporting Services], scale-out deployments
- encryption [Reporting Services]
- rskeymgmt utility
- scale-out deployments [Reporting Services]
ms.assetid: 53f1318d-bd2d-4c08-b19f-c8b698b5b3d3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ae4bdd6656cf5b29f8fd40fcf730f49a6de8f32e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683376"
---
# <a name="rskeymgmt-utility-ssrs"></a><span data-ttu-id="3d25a-102">Utilitário rskeymgmt (SSRS)</span><span class="sxs-lookup"><span data-stu-id="3d25a-102">rskeymgmt Utility (SSRS)</span></span>
  <span data-ttu-id="3d25a-103">Extrai, restaura, cria e exclui a chave simétrica usada para proteger dados confidenciais de servidor de relatório contra acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="3d25a-103">Extracts, restores, creates, and deletes the symmetric key used to protect sensitive report server data against unauthorized access.</span></span> <span data-ttu-id="3d25a-104">Esse utilitário também é usado para unir instâncias de servidor de relatório em uma implantação de expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-104">This utility is also used to join report server instances in a scale-out deployment.</span></span> <span data-ttu-id="3d25a-105">Uma *implantação em expansão de servidor de relatório* se refere a várias instâncias do servidor de relatório que compartilham um único banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-105">A *report server scale-out deployment* refers to multiple report server instances that share a single report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d25a-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3d25a-106">Syntax</span></span>  
  
```  
  
      rskeymgmt {-?}  
{-eextract}  
{-aapply}  
{-ddeleteall}  
{-srecreatekey}  
{-rremoveinstancekey}  
{-jjoinfarm}  
{-iinstance}  
{-ffile}  
{-pencryptionpassword}  
{-mremotecomputer}  
{-ninstancenameofremotecomputer}  
{-uadministratoruseraccount}  
{-vadministratorpassword}  
{-ttrace}  
```  
  
## <a name="arguments"></a><span data-ttu-id="3d25a-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3d25a-107">Arguments</span></span>  
 <span data-ttu-id="3d25a-108">**-?**</span><span class="sxs-lookup"><span data-stu-id="3d25a-108">**-?**</span></span>  
 <span data-ttu-id="3d25a-109">Exibe a sintaxe de argumentos **rskeymgmt** .</span><span class="sxs-lookup"><span data-stu-id="3d25a-109">Displays the syntax of **rskeymgmt** arguments.</span></span>  
  
 <span data-ttu-id="3d25a-110">**-e**</span><span class="sxs-lookup"><span data-stu-id="3d25a-110">**-e**</span></span>  
 <span data-ttu-id="3d25a-111">Extrai a chave simétrica usada para criptografar e descriptografar dados da instância do servidor de relatório, para que você possa copiá-los em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d25a-111">Extracts the symmetric key used to encrypt and decrypt data for the report server instance so that you can copy it to a file.</span></span>  
  
 <span data-ttu-id="3d25a-112">Esse argumento não exige um valor.</span><span class="sxs-lookup"><span data-stu-id="3d25a-112">This argument does not take a value.</span></span> <span data-ttu-id="3d25a-113">Porém, você deve incluir argumentos adicionais na linha de comando para concluir a extração.</span><span class="sxs-lookup"><span data-stu-id="3d25a-113">However, you must include additional arguments on the command line to complete the extraction.</span></span> <span data-ttu-id="3d25a-114">Os argumentos que você deve especificar incluem `-f` e `-p`.</span><span class="sxs-lookup"><span data-stu-id="3d25a-114">The arguments that you must specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="3d25a-115">**-a**</span><span class="sxs-lookup"><span data-stu-id="3d25a-115">**-a**</span></span>  
 <span data-ttu-id="3d25a-116">Substitui uma chave simétrica existente por uma cópia que você fornece em uma senha de arquivo de backup protegido.</span><span class="sxs-lookup"><span data-stu-id="3d25a-116">Replaces an existing symmetric key with a copy that you provide in a password protected backup file.</span></span> <span data-ttu-id="3d25a-117">Todas as instâncias da chave simétrica são atualizadas.</span><span class="sxs-lookup"><span data-stu-id="3d25a-117">All instances of the symmetric key are updated.</span></span>  
  
 <span data-ttu-id="3d25a-118">Esse argumento não exige um valor.</span><span class="sxs-lookup"><span data-stu-id="3d25a-118">This argument does not take a value.</span></span> <span data-ttu-id="3d25a-119">Porém, você deve incluir argumentos adicionais na linha de comando para selecionar o arquivo que contém a chave a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="3d25a-119">However, you must include additional arguments on the command line to select the file that contains the key to be applied.</span></span> <span data-ttu-id="3d25a-120">Os argumentos que você pode especificar incluem `-f` e `-p`.</span><span class="sxs-lookup"><span data-stu-id="3d25a-120">The arguments that you can specify include `-f` and`-p`.</span></span>  
  
 <span data-ttu-id="3d25a-121">**-d**</span><span class="sxs-lookup"><span data-stu-id="3d25a-121">**-d**</span></span>  
 <span data-ttu-id="3d25a-122">Exclui todas as instâncias de chave simétrica e todos os dados criptografados em um banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-122">Deletes all symmetric key instances and all encrypted data in a report server database.</span></span> <span data-ttu-id="3d25a-123">Esse argumento não exige um valor.</span><span class="sxs-lookup"><span data-stu-id="3d25a-123">This argument does not take a value.</span></span>  
  
 `-s`  
 <span data-ttu-id="3d25a-124">Gera uma chave simétrica nova e criptografa novamente todo o conteúdo criptografado usando a nova chave.</span><span class="sxs-lookup"><span data-stu-id="3d25a-124">Generates a new symmetric key and re-encrypts all encrypted content using the new key.</span></span> <span data-ttu-id="3d25a-125">Todas as instâncias da chave simétrica são regeneradas.</span><span class="sxs-lookup"><span data-stu-id="3d25a-125">All instances of the symmetric key are regenerated.</span></span>  
  
 `-j`  
 <span data-ttu-id="3d25a-126">Configura uma instância de servidor de relatório remota para compartilhar o banco de dados do servidor de relatório usado pela instância do servidor de relatório local.</span><span class="sxs-lookup"><span data-stu-id="3d25a-126">Configures a remote report server instance to share the report server database that is used by the local report server instance.</span></span>  
  
 <span data-ttu-id="3d25a-127">**-r**  *installationID*</span><span class="sxs-lookup"><span data-stu-id="3d25a-127">**-r**  *installationID*</span></span>  
 <span data-ttu-id="3d25a-128">Remove as informações de chave simétrica de uma instância de servidor de relatório específica, removendo assim o servidor do relatório de uma implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-128">Removes the symmetric key information for a specific report server instance, thereby removing the report server from a scale-out deployment.</span></span> <span data-ttu-id="3d25a-129">O *ID_instalação* é um valor GUID que pode ser localizado no arquivo RSReportserver.config.</span><span class="sxs-lookup"><span data-stu-id="3d25a-129">The *installationID* is a GUID value that can be found in the RSReportserver.config file.</span></span>  
  
 <span data-ttu-id="3d25a-130">`-f`  *Grupo*</span><span class="sxs-lookup"><span data-stu-id="3d25a-130">`-f`  *file*</span></span>  
 <span data-ttu-id="3d25a-131">Especifica um caminho totalmente qualificado ao arquivo que armazena uma cópia de backup das chaves simétricas.</span><span class="sxs-lookup"><span data-stu-id="3d25a-131">Specifies a fully qualified path to the file that stores a backup copy of the symmetric keys.</span></span>  
  
 <span data-ttu-id="3d25a-132">Para **rskeymgmt -e**, a chave simétrica é gravada no arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3d25a-132">For **rskeymgmt -e**, the symmetric key is written to the file you specify.</span></span>  
  
 <span data-ttu-id="3d25a-133">Para **rskeymgmt -a**, o valor da chave simétrica armazenado no arquivo é aplicado à instância do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-133">For **rskeymgmt -a**, the symmetric key value stored in the file is applied to the report server instance.</span></span>  
  
 <span data-ttu-id="3d25a-134">`-p`  *la*</span><span class="sxs-lookup"><span data-stu-id="3d25a-134">`-p`  *password*</span></span>  
 <span data-ttu-id="3d25a-135">(Necessário para `-f`) Especifica a senha usada para fazer backup ou para aplicar uma chave simétrica.</span><span class="sxs-lookup"><span data-stu-id="3d25a-135">(Required for `-f`) Specifies the password used to back up or apply a symmetric key.</span></span> <span data-ttu-id="3d25a-136">Esse valor não pode ficar em branco.</span><span class="sxs-lookup"><span data-stu-id="3d25a-136">This value cannot be empty.</span></span>  
  
 `-i`  
 <span data-ttu-id="3d25a-137">Especifica uma instância do servidor de relatório local.</span><span class="sxs-lookup"><span data-stu-id="3d25a-137">Specifies a local report server instance.</span></span> <span data-ttu-id="3d25a-138">Esse argumento será opcional se você instalou o servidor de relatório na instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (o valor padrão para `-i` é MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="3d25a-138">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-i` is MSSQLSERVER).</span></span> <span data-ttu-id="3d25a-139">Se você instalou o servidor de relatório como uma instância nomeada, `-i` será necessário.</span><span class="sxs-lookup"><span data-stu-id="3d25a-139">If you installed the report server as a named instance, `-i` is required.</span></span>  
  
 `-m`  
 <span data-ttu-id="3d25a-140">Especifica o nome do computador remoto que hospeda a instância do servidor de relatório que está sendo unido à implantação em expansão do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-140">Specifies the name of the remote computer that hosts the report server instance you are joining to the report server scale-out deployment.</span></span> <span data-ttu-id="3d25a-141">Use o nome do computador que o identifica em sua rede.</span><span class="sxs-lookup"><span data-stu-id="3d25a-141">Use the name of the computer that identifies it on your network.</span></span>  
  
 `-n`  
 <span data-ttu-id="3d25a-142">Especifica o nome da instância do servidor de relatório em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3d25a-142">Specifies the name of the report server instance on a remote computer.</span></span> <span data-ttu-id="3d25a-143">Esse argumento será opcional se você instalou o servidor de relatório na instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (o valor padrão para `-n` é MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="3d25a-143">This argument is optional if you installed the report server on the default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (the default value for `-n` is MSSQLSERVER).</span></span> <span data-ttu-id="3d25a-144">Se você instalou o servidor de relatório como uma instância nomeada, `-n` será necessário.</span><span class="sxs-lookup"><span data-stu-id="3d25a-144">If you installed the report server as a named instance, `-n` is required.</span></span>  
  
 <span data-ttu-id="3d25a-145">`-u`  *USERACCOUNT*</span><span class="sxs-lookup"><span data-stu-id="3d25a-145">`-u`  *useraccount*</span></span>  
 <span data-ttu-id="3d25a-146">Especifica a conta de administrador no computador remoto que você está unindo à implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-146">Specifies the administrator account on the remote computer that you are joining to the scale-out deployment.</span></span> <span data-ttu-id="3d25a-147">Se uma conta não for especificada, as credenciais do usuário atual serão usadas.</span><span class="sxs-lookup"><span data-stu-id="3d25a-147">If an account is not specified, the credentials of the current user are used.</span></span>  
  
 <span data-ttu-id="3d25a-148">`-v`  *la*</span><span class="sxs-lookup"><span data-stu-id="3d25a-148">`-v`  *password*</span></span>  
 <span data-ttu-id="3d25a-149">(Necessário para `-u`) Especifica a senha de uma conta de administrador no computador remoto que você quer unir à implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-149">(Required for `-u`) Specifies the password of an administrator account on the remote computer that you want to join to the scale-out deployment.</span></span>  
  
 <span data-ttu-id="3d25a-150">*rastreamento* **-t**  </span><span class="sxs-lookup"><span data-stu-id="3d25a-150">**-t**  *trace*</span></span>  
 <span data-ttu-id="3d25a-151">Produz mensagens de erro para o log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="3d25a-151">Outputs error messages to the trace log.</span></span> <span data-ttu-id="3d25a-152">Esse argumento não exige um valor.</span><span class="sxs-lookup"><span data-stu-id="3d25a-152">This argument does not take a value.</span></span> <span data-ttu-id="3d25a-153">Para obter mais informações, consulte [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3d25a-153">For more information, see [Report Server Service Trace Log](../report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="3d25a-154">Permissões</span><span class="sxs-lookup"><span data-stu-id="3d25a-154">Permissions</span></span>  
 <span data-ttu-id="3d25a-155">Você deve ter permissões de administrador de sistema local para executar a ferramenta, e é necessário executá-la localmente no computador que hospeda o servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-155">You must be a local administrator to run the tool, and you must run it locally on the computer that hosts the report server.</span></span> <span data-ttu-id="3d25a-156">O utilitário rskeymgmt funciona com a instância local do Servidor de Relatório do Windows (o utilitário não pode se conectar a instâncias remotas do serviço Servidor de Relatório do Windows, portanto não pode ser usado para gerenciar chaves de criptografia em uma instância de servidor remota).</span><span class="sxs-lookup"><span data-stu-id="3d25a-156">The rskeymgmt utility works with the local Report Server Windows instance (the utility cannot connect to remote instances of the Report Server Windows service so it cannot be used to manage the encryption keys of a remote report server instance).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3d25a-157">Se você estiver usando os argumentos `-u` e `-v`, especifique uma conta que tenha permissões de administrador no computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3d25a-157">If you are using the `-u` and `-v` arguments, be sure to specify an account that has administrator permissions on the remote computer.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3d25a-158">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3d25a-158">Examples</span></span>  
 <span data-ttu-id="3d25a-159">Os exemplos a seguir ilustram as maneiras de usar o **rskeymgmt**.</span><span class="sxs-lookup"><span data-stu-id="3d25a-159">The following examples illustrate ways of using **rskeymgmt**.</span></span> <span data-ttu-id="3d25a-160">Os exemplos a seguir mostram como extrair, restaurar e excluir chaves de criptografia e como configurar uma implantação em expansão no servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-160">The following examples show how to extract, restore, and delete encryption keys, and how to configure a report server scale-out deployment.</span></span>  
  
#### <a name="extracting-encryption-keys"></a><span data-ttu-id="3d25a-161">Extraindo chaves de criptografia</span><span class="sxs-lookup"><span data-stu-id="3d25a-161">Extracting Encryption Keys</span></span>  
 <span data-ttu-id="3d25a-162">Esse exemplo mostra como criar uma cópia de backup da chave de criptografia e salvá-la em um arquivo protegido por senha em um disquete.</span><span class="sxs-lookup"><span data-stu-id="3d25a-162">This example shows how to create a backup copy of the encryption key and save it to a password-protected file on a floppy disk.</span></span> <span data-ttu-id="3d25a-163">Se o servidor de relatório for instalado como uma instância nomeada, adicione o argumento `-i`.</span><span class="sxs-lookup"><span data-stu-id="3d25a-163">If the report server is installed as a named instance, add the `-i` argument.</span></span>  
  
```  
rskeymgmt -e -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="restoring-encryption-keys"></a><span data-ttu-id="3d25a-164">Restaurando chaves de criptografia</span><span class="sxs-lookup"><span data-stu-id="3d25a-164">Restoring Encryption Keys</span></span>  
 <span data-ttu-id="3d25a-165">Este exemplo mostra como substituir a chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="3d25a-165">This example shows how to replace the encryption key.</span></span> <span data-ttu-id="3d25a-166">Você deve especificar o local da cópia de backup da chave e a senha que desbloqueia o arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d25a-166">You must specify the location of the backup copy of the key and the password that unlocks the file.</span></span>  
  
```  
rskeymgmt -a -f a:\backupkey\keys -p <password>  
```  
  
#### <a name="deleting-encryption-keys-and-encrypted-content"></a><span data-ttu-id="3d25a-167">Excluindo chaves de criptografia e conteúdo criptografado</span><span class="sxs-lookup"><span data-stu-id="3d25a-167">Deleting Encryption Keys and Encrypted Content</span></span>  
 <span data-ttu-id="3d25a-168">Este exemplo mostra como excluir todas as chaves de criptografia armazenadas em um servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-168">This example shows how to delete all encryption keys stored in a report server.</span></span> <span data-ttu-id="3d25a-169">Se a sua instalação for uma implantação em expansão do servidor de relatório, as chaves de criptografia de todas as instâncias do servidor de relatório incluídas na implantação serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="3d25a-169">If your installation is a report server scale-out deployment, the encryption keys for all report server instances that are included in the deployment will be deleted.</span></span> <span data-ttu-id="3d25a-170">A exclusão de uma chave de criptografia exclui também qualquer valor criptografado existente no banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-170">Deleting an encryption key also deletes any existing encrypted values in the report server database.</span></span> <span data-ttu-id="3d25a-171">Para obter mais informações sobre conteúdo criptografado, consulte [Armazenar dados criptografados do servidor de relatório &#40;Gerenciador de Configurações do SSRS&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span><span class="sxs-lookup"><span data-stu-id="3d25a-171">For more information about encrypted content, see [Store Encrypted Report Server Data &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md).</span></span>  
  
```  
rskeymgmt -d  
```  
  
#### <a name="joining-a-remote-report-server-named-instance-to-a-scale-out-deployment"></a><span data-ttu-id="3d25a-172">Unindo uma instância nomeada de servidor de relatório remota a uma implantação em expansão</span><span class="sxs-lookup"><span data-stu-id="3d25a-172">Joining a Remote Report Server Named Instance to a Scale-out Deployment</span></span>  
 <span data-ttu-id="3d25a-173">Este exemplo mostra como adicionar uma instância de servidor de relatório instalada em um computador remoto a uma implantação em expansão de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-173">This example shows how to add a report server instance that is installed on a remote computer to a report server scale-out deployment.</span></span> <span data-ttu-id="3d25a-174">Você deve executar o comando em um dos computadores já configurado para usar o banco de dados compartilhado.</span><span class="sxs-lookup"><span data-stu-id="3d25a-174">You must run the command on one of the computers that is already configured to use the shared database.</span></span> <span data-ttu-id="3d25a-175">Os argumentos de comando especificam a instância do servidor de relatório remota que você quer adicionar à implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-175">The command arguments specify the remote report server instance you want to join to the scale-out deployment.</span></span>  
  
```  
rskeymgmt -j -m <remotecomputer> -n <namedreportserverinstance> -u <administratoraccount> -v <administratorpassword>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3d25a-176">Uma implantação em expansão de servidor de relatório se refere a um modelo de implantação onde várias instâncias do servidor de relatório compartilham o mesmo banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-176">A report server scale-out deployment refers to a deployment model where multiple report server instances share the same report server database.</span></span> <span data-ttu-id="3d25a-177">Um banco de dados do servidor de relatório pode ser usado por qualquer instância que armazena suas chaves simétricas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3d25a-177">A report server database can be used by any report server instance that stores its symmetric keys in the database.</span></span> <span data-ttu-id="3d25a-178">Por exemplo, se um banco de dados do servidor de relatório contiver informações de chave para três instâncias do servidor de relatório, todas as três instâncias serão consideradas membros da mesma implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-178">For example, if a report server database contains key information for three report server instances, all three instances are considered to members of the same scale-out deployment.</span></span>  
  
#### <a name="joining-report-server-instances-on-the-same-computer"></a><span data-ttu-id="3d25a-179">Unindo instâncias do servidor de relatório no mesmo computador</span><span class="sxs-lookup"><span data-stu-id="3d25a-179">Joining Report Server Instances on the Same Computer</span></span>  
 <span data-ttu-id="3d25a-180">Você pode criar uma implantação em expansão para várias de instâncias do servidor de relatório instaladas no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="3d25a-180">You can create a scale-out deployment from multiple report server instances that are installed on the same computer.</span></span> <span data-ttu-id="3d25a-181">Não defina os argumentos `-u` e `-v` se você estiver unindo instâncias do servidor de relatório instaladas localmente.</span><span class="sxs-lookup"><span data-stu-id="3d25a-181">Do not set the `-u` and `-v` arguments if you are joining report server instances that are installed locally.</span></span> <span data-ttu-id="3d25a-182">Os argumentos `-u` e `-v` só são usados quando você estiver unindo uma instância de um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3d25a-182">The `-u` and `-v` arguments are used only when you are joining an instance from a remote computer.</span></span> <span data-ttu-id="3d25a-183">Se você especificar os argumentos, receberá o seguinte erro: "Credenciais de usuário não podem ser usadas para conexões locais".</span><span class="sxs-lookup"><span data-stu-id="3d25a-183">If you specify the arguments, you will get the following error: "User credentials cannot be used for local connections."</span></span>  
  
 <span data-ttu-id="3d25a-184">O exemplo a seguir ilustra a sintaxe para criar uma implantação em expansão que usa várias instâncias locais.</span><span class="sxs-lookup"><span data-stu-id="3d25a-184">The following example illustrates the syntax for creating a scale-out deployment using multiple local instances.</span></span> <span data-ttu-id="3d25a-185">Neste exemplo, <`initializedinstance`> é o nome de uma instância que já foi inicializada para usar o banco de dados do servidor de relatório e <`newinstance`> é o nome da instância que você deseja adicionar à implantação:</span><span class="sxs-lookup"><span data-stu-id="3d25a-185">In this example, <`initializedinstance`> is the name of an instance that is already initialized to use the report server database, and <`newinstance`> is the name of the instance that you want to add to the deployment:</span></span>  
  
```  
rskeymgmt -j -i <initializedinstance> -m <computer name> -n <newinstance>  
```  
  
#### <a name="removing-encryption-keys-for-a-single-report-server-in-a-scale-out-deployment"></a><span data-ttu-id="3d25a-186">Removendo chaves de criptografia para um servidor de relatório único em uma implantação em expansão</span><span class="sxs-lookup"><span data-stu-id="3d25a-186">Removing Encryption Keys for a Single Report Server in a Scale-out Deployment</span></span>  
 <span data-ttu-id="3d25a-187">Este exemplo mostra como remover as chaves de criptografia para um servidor de relatório único em uma implantação em expansão de servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-187">This example shows how to remove the encryption keys for a single report server in a report server scale-out deployment.</span></span> <span data-ttu-id="3d25a-188">As chaves são removidas do banco de dados do servidor de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d25a-188">The keys are removed from the report server database.</span></span> <span data-ttu-id="3d25a-189">Uma vez que as chaves da instância do servidor de relatório são removidas, aquela instância do servidor de relatório não poderá mais acessar dados criptografados no banco de dados, removendo-os efetivamente da implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-189">Once the keys for that report server instance are removed, that report server instance can no longer access encrypted data in the database, effectively removing it from the scale-out deployment.</span></span>  
  
 <span data-ttu-id="3d25a-190">A remoção de uma instância de servidor de relatório de uma implantação em expansão exige que você especifique uma ID de instalação.</span><span class="sxs-lookup"><span data-stu-id="3d25a-190">Removing a report server instance from a scale-out deployment requires you to specify an installation ID.</span></span> <span data-ttu-id="3d25a-191">A ID de instalação é um GUID armazenado no arquivo RSReportserver.config da instância do servidor de relatório para o qual você quer remover as chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="3d25a-191">The installation ID is a GUID stored in the RSReportserver.config file of the report server instance for which you want to remove encryption keys.</span></span> <span data-ttu-id="3d25a-192">Você deve executar o comando a seguir no computador que você quer remover da implantação em expansão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-192">You must run the following command on the computer that you want to remove from the scale-out deployment.</span></span> <span data-ttu-id="3d25a-193">Se o servidor de relatório estiver instalado como uma instância nomeada, use o argumento `-i` para especificar a instância.</span><span class="sxs-lookup"><span data-stu-id="3d25a-193">If the report server is installed as a named instance, use the `-i` argument to specify the instance.</span></span> <span data-ttu-id="3d25a-194">Para obter mais informações, consulte [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="3d25a-194">For more information, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span>  
  
```  
rskeymgmt -r <installationID>  
```  
  
## <a name="file-location"></a><span data-ttu-id="3d25a-195">Localização do arquivo</span><span class="sxs-lookup"><span data-stu-id="3d25a-195">File Location</span></span>  
 <span data-ttu-id="3d25a-196">O Rskeymgmt.exe está localizado em \*\* \<*drive*> : \Program Files\Microsoft SQL Server\110\Tools\Binn\*\* ou em \*\* \<*drive*> : \Program Files (x86) \Microsoft SQL Server\110\Tools\Binn\*\*.</span><span class="sxs-lookup"><span data-stu-id="3d25a-196">Rskeymgmt.exe is located at **\<*drive*>:\Program Files\Microsoft SQL Server\110\Tools\Binn** or at **\<*drive*>:\Program Files (x86)\Microsoft SQL Server\110\Tools\Binn**.</span></span> <span data-ttu-id="3d25a-197">Você pode executar o utilitário de qualquer pasta em seu sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3d25a-197">You can run the utility from any folder on your file system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d25a-198">Comentários</span><span class="sxs-lookup"><span data-stu-id="3d25a-198">Remarks</span></span>  
 <span data-ttu-id="3d25a-199">Um servidor de relatório criptografa credenciais armazenadas e informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="3d25a-199">A report server encrypts stored credentials and connection information.</span></span> <span data-ttu-id="3d25a-200">Uma chave pública e uma chave simétrica são usadas para criptografar dados.</span><span class="sxs-lookup"><span data-stu-id="3d25a-200">A public key and a symmetric key are used to encrypt data.</span></span> <span data-ttu-id="3d25a-201">Um banco de dados do servidor de relatório deve ter chaves válidas para que o servidor de relatório seja executado.</span><span class="sxs-lookup"><span data-stu-id="3d25a-201">A report server database must have valid keys in order for the report server to run.</span></span> <span data-ttu-id="3d25a-202">Você pode usar **rskeymgmt** para fazer backup, excluir ou restaurar as chaves.</span><span class="sxs-lookup"><span data-stu-id="3d25a-202">You can use **rskeymgmt** to back up, delete, or restore the keys.</span></span> <span data-ttu-id="3d25a-203">Se as chaves não puderem ser restauradas, essa ferramenta fornecerá um modo de excluir conteúdo criptografado que não pode mais ser usado.</span><span class="sxs-lookup"><span data-stu-id="3d25a-203">If the keys cannot be restored, this tool provides a way to delete encrypted content that can no longer be used.</span></span>  
  
 <span data-ttu-id="3d25a-204">O utilitário **rskeymgmt** é usado para gerenciar o conjunto de chaves definido durante a instalação ou durante a inicialização.</span><span class="sxs-lookup"><span data-stu-id="3d25a-204">The **rskeymgmt** utility is used to manage the key set that is defined during Setup or during initialization.</span></span> <span data-ttu-id="3d25a-205">Ele se conecta ao serviço Servidor de Relatório do Windows através de um ponto de extremidade RPC (Chamada de Procedimento Remoto).</span><span class="sxs-lookup"><span data-stu-id="3d25a-205">It connects to the local Report Server Windows service through a Remote Procedure Call (RPC) endpoint.</span></span> <span data-ttu-id="3d25a-206">O serviço Servidor de Relatório do Windows deve estar em execução para que esse utilitário funcione.</span><span class="sxs-lookup"><span data-stu-id="3d25a-206">The Report Server Windows service must be running in order for this utility to work.</span></span>  
  
 <span data-ttu-id="3d25a-207">Para obter mais informações sobre as chaves de criptografia, consulte [Configurar e gerenciar chaves de criptografia &#40; 	Gerenciador de Configurações do SSRS&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) e [Inicializar um servidor de relatório &#40;Gerenciador de Configurações do SSRS&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="3d25a-207">For more information about the encryption keys, see [Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md) and [Initialize a Report Server &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-encryption-keys-initialize-a-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d25a-208">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d25a-208">See Also</span></span>  
 <span data-ttu-id="3d25a-209">[Configurar uma implantação em expansão do servidor de relatório no modo nativo &#40;Configuration Manager SSRS&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="3d25a-209">[Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md) </span></span>  
 <span data-ttu-id="3d25a-210">[Servidor de relatório do Reporting Services &#40;Modo Nativo&#41;](../report-server/reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3d25a-210">[Reporting Services Report Server &#40;Native Mode&#41;](../report-server/reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="3d25a-211">[Utilitários de prompt de comando do servidor de relatório &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3d25a-211">[Report Server Command Prompt Utilities &#40;SSRS&#41;](report-server-command-prompt-utilities-ssrs.md) </span></span>  
 [<span data-ttu-id="3d25a-212">Configurar e gerenciar chaves de criptografia &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="3d25a-212">Configure and Manage Encryption Keys &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-encryption-keys-manage-encryption-keys.md)  
  
  
