<h1>Kustomize API reference</h1>
<p>Packages:</p>
<ul class="simple">
<li>
<a href="#kustomize.toolkit.fluxcd.io%2fv1beta1">kustomize.toolkit.fluxcd.io/v1beta1</a>
</li>
</ul>
<h2 id="kustomize.toolkit.fluxcd.io/v1beta1">kustomize.toolkit.fluxcd.io/v1beta1</h2>
<p>Package v1beta1 contains API Schema definitions for the kustomize v1beta1 API group</p>
Resource Types:
<ul class="simple"><li>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Kustomization">Kustomization</a>
</li></ul>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.Kustomization">Kustomization
</h3>
<p>Kustomization is the Schema for the kustomizations API.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code><br>
string</td>
<td>
<code>kustomize.toolkit.fluxcd.io/v1beta1</code>
</td>
</tr>
<tr>
<td>
<code>kind</code><br>
string
</td>
<td>
<code>Kustomization</code>
</td>
</tr>
<tr>
<td>
<code>metadata</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta
</a>
</em>
</td>
<td>
Refer to the Kubernetes API documentation for the fields of the
<code>metadata</code> field.
</td>
</tr>
<tr>
<td>
<code>spec</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">
KustomizationSpec
</a>
</em>
</td>
<td>
<br/>
<br/>
<table>
<tr>
<td>
<code>dependsOn</code><br>
<em>
<a href="https://godoc.org/github.com/fluxcd/pkg/runtime/dependency#CrossNamespaceDependencyReference">
[]Runtime dependency.CrossNamespaceDependencyReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>DependsOn may contain a dependency.CrossNamespaceDependencyReference slice
with references to Kustomization resources that must be ready before this
Kustomization can be reconciled.</p>
</td>
</tr>
<tr>
<td>
<code>decryption</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Decryption">
Decryption
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Decrypt Kubernetes secrets before applying them on the cluster.</p>
</td>
</tr>
<tr>
<td>
<code>interval</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<p>The interval at which to reconcile the kustomization.</p>
</td>
</tr>
<tr>
<td>
<code>kubeConfig</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KubeConfig">
KubeConfig
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The KubeConfig for reconciling the Kustomization on a remote cluster.</p>
</td>
</tr>
<tr>
<td>
<code>path</code><br>
<em>
string
</em>
</td>
<td>
<p>Path to the directory containing the kustomization file.</p>
</td>
</tr>
<tr>
<td>
<code>prune</code><br>
<em>
bool
</em>
</td>
<td>
<p>Prune enables garbage collection.</p>
</td>
</tr>
<tr>
<td>
<code>healthChecks</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceObjectReference">
[]CrossNamespaceObjectReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>A list of resources to be included in the health assessment.</p>
</td>
</tr>
<tr>
<td>
<code>serviceAccount</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.ServiceAccount">
ServiceAccount
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The Kubernetes service account used for applying the kustomization.</p>
</td>
</tr>
<tr>
<td>
<code>sourceRef</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceSourceReference">
CrossNamespaceSourceReference
</a>
</em>
</td>
<td>
<p>Reference of the source where the kustomization file is.</p>
</td>
</tr>
<tr>
<td>
<code>suspend</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>This flag tells the controller to suspend subsequent kustomize executions,
it does not apply to already started executions. Defaults to false.</p>
</td>
</tr>
<tr>
<td>
<code>targetNamespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>TargetNamespace sets or overrides the namespace in the
kustomization.yaml file.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout for validation, apply and health checking operations.
Defaults to &lsquo;Interval&rsquo; duration.</p>
</td>
</tr>
<tr>
<td>
<code>validation</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Validate the Kubernetes objects before applying them on the cluster.
The validation strategy can be &lsquo;client&rsquo; (local dry-run) or &lsquo;server&rsquo; (APIServer dry-run).</p>
</td>
</tr>
</table>
</td>
</tr>
<tr>
<td>
<code>status</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationStatus">
KustomizationStatus
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceObjectReference">CrossNamespaceObjectReference
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec</a>)
</p>
<p>CrossNamespaceObjectReference contains enough information to let you locate the
typed referenced object at cluster level</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>API version of the referent, defaults to &lsquo;apps/v1&rsquo;</p>
</td>
</tr>
<tr>
<td>
<code>kind</code><br>
<em>
string
</em>
</td>
<td>
<p>Kind of the referent</p>
</td>
</tr>
<tr>
<td>
<code>name</code><br>
<em>
string
</em>
</td>
<td>
<p>Name of the referent</p>
</td>
</tr>
<tr>
<td>
<code>namespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Namespace of the referent</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceSourceReference">CrossNamespaceSourceReference
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec</a>)
</p>
<p>CrossNamespaceSourceReference contains enough information to let you locate the
typed referenced object at cluster level</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>API version of the referent</p>
</td>
</tr>
<tr>
<td>
<code>kind</code><br>
<em>
string
</em>
</td>
<td>
<p>Kind of the referent</p>
</td>
</tr>
<tr>
<td>
<code>name</code><br>
<em>
string
</em>
</td>
<td>
<p>Name of the referent</p>
</td>
</tr>
<tr>
<td>
<code>namespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Namespace of the referent, defaults to the Kustomization namespace</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.Decryption">Decryption
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec</a>)
</p>
<p>Decryption defines how decryption is handled for Kubernetes manifests.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>provider</code><br>
<em>
string
</em>
</td>
<td>
<p>Provider is the name of the decryption engine.</p>
</td>
</tr>
<tr>
<td>
<code>secretRef</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#localobjectreference-v1-core">
Kubernetes core/v1.LocalObjectReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The secret name containing the private OpenPGP keys used for decryption.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.KubeConfig">KubeConfig
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec</a>)
</p>
<p>KubeConfig references a Kubernetes secret generated by CAPI.
that contains a kubeconfig file.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>secretRef</code><br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#localobjectreference-v1-core">
Kubernetes core/v1.LocalObjectReference
</a>
</em>
</td>
<td>
<p>The secret name containing a &lsquo;value&rsquo; key with the kubeconfig file as the value.
This secret must be in the same Namespace as the Kustomization.
KubeConfig secrets maintained by Cluster API bootstrap providers can be used here.
(ex: If your CAPI Cluster&rsquo;s name is <code>stage</code>, set this to <code>stage-kubeconfig</code>.
Ensure the Kustomization is in the same Namespace as the Cluster object.
Ref: <a href="https://github.com/kubernetes-sigs/cluster-api/blob/release-0.3/util/secret/consts.go#L24)">https://github.com/kubernetes-sigs/cluster-api/blob/release-0.3/util/secret/consts.go#L24)</a>
The reconciliation clients are regularly refreshed from the Secret, so
rotating kubeconfigs for KaaS control-planes from cloud-providers are supported.
These kubeconfigs follow the same design constraints as Cluster API.
It is recommended that kubeconfigs be self-contained, and the Secret be
regularly updated if credentials such as a cloud-access-token expire.
Cloud-specific <code>cmd-path</code> auth helpers will not function without adding
binaries and credentials to the kustomize-controller Pod.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Kustomization">Kustomization</a>)
</p>
<p>KustomizationSpec defines the desired state of a kustomization.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>dependsOn</code><br>
<em>
<a href="https://godoc.org/github.com/fluxcd/pkg/runtime/dependency#CrossNamespaceDependencyReference">
[]Runtime dependency.CrossNamespaceDependencyReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>DependsOn may contain a dependency.CrossNamespaceDependencyReference slice
with references to Kustomization resources that must be ready before this
Kustomization can be reconciled.</p>
</td>
</tr>
<tr>
<td>
<code>decryption</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Decryption">
Decryption
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Decrypt Kubernetes secrets before applying them on the cluster.</p>
</td>
</tr>
<tr>
<td>
<code>interval</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<p>The interval at which to reconcile the kustomization.</p>
</td>
</tr>
<tr>
<td>
<code>kubeConfig</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KubeConfig">
KubeConfig
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The KubeConfig for reconciling the Kustomization on a remote cluster.</p>
</td>
</tr>
<tr>
<td>
<code>path</code><br>
<em>
string
</em>
</td>
<td>
<p>Path to the directory containing the kustomization file.</p>
</td>
</tr>
<tr>
<td>
<code>prune</code><br>
<em>
bool
</em>
</td>
<td>
<p>Prune enables garbage collection.</p>
</td>
</tr>
<tr>
<td>
<code>healthChecks</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceObjectReference">
[]CrossNamespaceObjectReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>A list of resources to be included in the health assessment.</p>
</td>
</tr>
<tr>
<td>
<code>serviceAccount</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.ServiceAccount">
ServiceAccount
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The Kubernetes service account used for applying the kustomization.</p>
</td>
</tr>
<tr>
<td>
<code>sourceRef</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.CrossNamespaceSourceReference">
CrossNamespaceSourceReference
</a>
</em>
</td>
<td>
<p>Reference of the source where the kustomization file is.</p>
</td>
</tr>
<tr>
<td>
<code>suspend</code><br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>This flag tells the controller to suspend subsequent kustomize executions,
it does not apply to already started executions. Defaults to false.</p>
</td>
</tr>
<tr>
<td>
<code>targetNamespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>TargetNamespace sets or overrides the namespace in the
kustomization.yaml file.</p>
</td>
</tr>
<tr>
<td>
<code>timeout</code><br>
<em>
<a href="https://godoc.org/k8s.io/apimachinery/pkg/apis/meta/v1#Duration">
Kubernetes meta/v1.Duration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Timeout for validation, apply and health checking operations.
Defaults to &lsquo;Interval&rsquo; duration.</p>
</td>
</tr>
<tr>
<td>
<code>validation</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Validate the Kubernetes objects before applying them on the cluster.
The validation strategy can be &lsquo;client&rsquo; (local dry-run) or &lsquo;server&rsquo; (APIServer dry-run).</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.KustomizationStatus">KustomizationStatus
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Kustomization">Kustomization</a>)
</p>
<p>KustomizationStatus defines the observed state of a kustomization.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>observedGeneration</code><br>
<em>
int64
</em>
</td>
<td>
<em>(Optional)</em>
<p>ObservedGeneration is the last reconciled generation.</p>
</td>
</tr>
<tr>
<td>
<code>conditions</code><br>
<em>
<a href="https://godoc.org/github.com/fluxcd/pkg/apis/meta#Condition">
[]github.com/fluxcd/pkg/apis/meta.Condition
</a>
</em>
</td>
<td>
<em>(Optional)</em>
</td>
</tr>
<tr>
<td>
<code>lastAppliedRevision</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>The last successfully applied revision.
The revision format for Git sources is <branch|tag>/<commit-sha>.</p>
</td>
</tr>
<tr>
<td>
<code>lastAttemptedRevision</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastAttemptedRevision is the revision of the last reconciliation attempt.</p>
</td>
</tr>
<tr>
<td>
<code>lastHandledReconcileAt</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastHandledReconcileAt is the last manual reconciliation request (by
annotating the Kustomization) handled by the reconciler.</p>
</td>
</tr>
<tr>
<td>
<code>snapshot</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Snapshot">
Snapshot
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>The last successfully applied revision metadata.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.ServiceAccount">ServiceAccount
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationSpec">KustomizationSpec</a>)
</p>
<p>ServiceAccount defines a reference to a Kubernetes service account.</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code><br>
<em>
string
</em>
</td>
<td>
<p>Name is the name of the service account being referenced.</p>
</td>
</tr>
<tr>
<td>
<code>namespace</code><br>
<em>
string
</em>
</td>
<td>
<p>Namespace is the namespace of the service account being referenced.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.Snapshot">Snapshot
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.KustomizationStatus">KustomizationStatus</a>)
</p>
<p>Snapshot holds the metadata of the Kubernetes objects
generated for a source revision</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>checksum</code><br>
<em>
string
</em>
</td>
<td>
<p>The manifests sha1 checksum.</p>
</td>
</tr>
<tr>
<td>
<code>entries</code><br>
<em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.SnapshotEntry">
[]SnapshotEntry
</a>
</em>
</td>
<td>
<p>A list of Kubernetes kinds grouped by namespace.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<h3 id="kustomize.toolkit.fluxcd.io/v1beta1.SnapshotEntry">SnapshotEntry
</h3>
<p>
(<em>Appears on:</em>
<a href="#kustomize.toolkit.fluxcd.io/v1beta1.Snapshot">Snapshot</a>)
</p>
<p>Snapshot holds the metadata of namespaced
Kubernetes objects</p>
<div class="md-typeset__scrollwrap">
<div class="md-typeset__table">
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>namespace</code><br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>The namespace of this entry.</p>
</td>
</tr>
<tr>
<td>
<code>kinds</code><br>
<em>
map[string]string
</em>
</td>
<td>
<p>The list of Kubernetes kinds.</p>
</td>
</tr>
</tbody>
</table>
</div>
</div>
<div class="admonition note">
<p class="last">This page was automatically generated with <code>gen-crd-api-reference-docs</code></p>
</div>
