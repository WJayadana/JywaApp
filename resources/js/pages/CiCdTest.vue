<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import { CheckCircle, Cloud, Rocket, RefreshCw } from 'lucide-vue-next';
import { onMounted } from 'vue';

// const deploymentStatus = ref('completed');
const lastDeployTime = new Date().toLocaleString();

onMounted(() => {
    // Subtle entry animation effect
});
</script>

<template>
    <Head title="CI/CD Test Page" />

    <div class="min-h-screen bg-[#0a0a0b] text-white flex flex-col items-center justify-center p-6 font-sans selection:bg-cyan-500/30">
        <!-- Background Ambient Glow -->
        <div class="fixed inset-0 overflow-hidden pointer-events-none">
            <div class="absolute top-[-25%] left-[-10%] w-[50%] h-[50%] bg-cyan-500/10 rounded-full blur-[120px] animate-pulse"></div>
            <div class="absolute bottom-[-25%] right-[-10%] w-[50%] h-[50%] bg-blue-600/10 rounded-full blur-[120px] animate-pulse" style="animation-delay: 2s"></div>
        </div>

        <!-- Main Card -->
        <div class="relative w-full max-w-2xl bg-white/3 border border-white/8 backdrop-blur-xl rounded-[2.5rem] p-8 md:p-12 shadow-2xl overflow-hidden group">
            <!-- Animated Border (Hover effect) -->
            <div class="absolute inset-0 bg-linear-to-tr from-cyan-500/0 via-cyan-500/0 to-cyan-500/20 opacity-0 group-hover:opacity-100 transition-opacity duration-700 pointer-events-none"></div>

            <div class="relative flex flex-col items-center text-center space-y-8">
                <!-- Icon Header -->
                <div class="relative">
                    <div class="absolute inset-0 bg-cyan-500/20 blur-2xl rounded-full scale-150 animate-pulse"></div>
                    <div class="relative h-24 w-24 bg-linear-to-br from-cyan-400 to-blue-600 rounded-2xl flex items-center justify-center shadow-lg transform rotate-3 hover:rotate-0 transition-transform duration-500">
                        <Rocket class="h-12 w-12 text-white" />
                    </div>
                </div>

                <!-- Content -->
                <div class="space-y-3">
                    <h1 class="text-4xl md:text-5xl font-bold tracking-tight bg-clip-text text-transparent bg-linear-to-b from-white to-white/60">
                        CI/CD Test Successful
                    </h1>
                    <p class="text-lg text-white/50 max-w-md mx-auto leading-relaxed">
                        Jika Anda melihat halaman ini, berarti pipeline deployment Anda berjalan dengan sempurna di server produksi.
                    </p>
                </div>

                <!-- Status Badge Grid -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 w-full">
                    <div class="flex items-center gap-4 bg-white/5 border border-white/5 rounded-2xl p-4 transition-colors hover:bg-white/8">
                        <div class="h-10 w-10 bg-green-500/20 rounded-xl flex items-center justify-center">
                            <CheckCircle class="h-6 w-6 text-green-400" />
                        </div>
                        <div class="text-left">
                            <p class="text-xs font-medium text-white/40 uppercase tracking-widest">Build Status</p>
                            <p class="text-sm font-semibold text-white/90">Success</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-4 bg-white/5 border border-white/5 rounded-2xl p-4 transition-colors hover:bg-white/8">
                        <div class="h-10 w-10 bg-blue-500/20 rounded-xl flex items-center justify-center">
                            <Cloud class="h-6 w-6 text-blue-400" />
                        </div>
                        <div class="text-left">
                            <p class="text-xs font-medium text-white/40 uppercase tracking-widest">Environment</p>
                            <p class="text-sm font-semibold text-white/90">Production</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-4 bg-white/5 border border-white/5 rounded-2xl p-4 transition-colors hover:bg-white/8">
                        <div class="h-10 w-10 bg-cyan-500/20 rounded-xl flex items-center justify-center">
                            <RefreshCw class="h-6 w-6 text-cyan-400" />
                        </div>
                        <div class="text-left">
                            <p class="text-xs font-medium text-white/40 uppercase tracking-widest">Last Deploy</p>
                            <p class="text-sm font-semibold text-white/90 truncate">{{ lastDeployTime }}</p>
                        </div>
                    </div>

                    <div class="flex items-center gap-4 bg-white/5 border border-white/5 rounded-2xl p-4 transition-colors hover:bg-white/8">
                        <div class="h-10 w-10 bg-purple-500/20 rounded-xl flex items-center justify-center">
                            <div class="h-3 w-3 bg-purple-400 rounded-full animate-ping"></div>
                        </div>
                        <div class="text-left">
                            <p class="text-xs font-medium text-white/40 uppercase tracking-widest">Pipeline</p>
                            <p class="text-sm font-semibold text-white/90">Live & Monitoring</p>
                        </div>
                    </div>
                </div>

                <!-- Footer Action -->
                <div class="pt-4">
                    <a href="/" class="group relative inline-flex items-center justify-center px-8 py-3 font-semibold text-white transition-all duration-200 bg-white/10 hover:bg-white/20 rounded-full border border-white/10 focus:outline-none">
                        Kembali ke Home
                    </a>
                </div>
            </div>
        </div>

        <!-- System Meta -->
        <div class="mt-8 text-white/20 text-xs font-mono tracking-widest uppercase">
            System ID: JYWA-{{ Math.random().toString(36).substr(2, 9).toUpperCase() }}
        </div>
    </div>
</template>

<style scoped>
@keyframes pulse-slow {
  0%, 100% { opacity: 0.1; }
  50% { opacity: 0.2; }
}

.animate-pulse-slow {
  animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
</style>
