<script setup lang="ts">
import { ref, type Ref } from 'vue';

interface Teacher {
    teacherName: string,
    surname: string,
    dni: string,
    subjects: Array<string>,
    doc: boolean
}

const teacher: Ref<Teacher> = ref({
    teacherName: '',
    surname: '',
    dni: '',
    subjects: [],
    doc: false
})

const teachers: Ref<Array<Teacher>> = ref([]);
const subject: Ref<string> = ref('')

const handleSubject = (): void => {
    teacher.value.subjects.push(subject.value)
    subject.value = ''
}

const handleAddTeacher = (): void => {
    teachers.value.push({
        teacherName: teacher.value.teacherName,
        surname: teacher.value.surname,
        dni: teacher.value.dni,
        subjects: teacher.value.subjects,
        doc: teacher.value.doc
    })

    teacher.value.teacherName = ''
    teacher.value.surname = ''
    teacher.value.dni = ''
    teacher.value.subjects = []
    teacher.value.doc = false
}
</script>

<template>
    <section>
        <h3>Añadir profesor</h3>
        <div>
            <label for="">Nombres:</label>
            <input type="text" v-model="teacher.teacherName">
        </div>

        <div>
            <label for="">Apellidos:</label>
            <input type="text" v-model="teacher.surname">
        </div>

        <div>
            <label for="">DNI:</label>
            <input type="text" v-model="teacher.dni">
        </div>

        <div>
            <label for="">Materias:</label>
            <input type="text" v-model="subject">
            <button @click="handleSubject()">Agregar</button>
            <div>
                <ul>
                    <li v-for="(elm, index) in teacher.subjects" :key="index">{{ elm }}</li>
                </ul>
            </div>
        </div>

        <input type="checkbox" v-model="teacher.doc"> Documentacion Entregada
        <button @click="handleAddTeacher()">Agregar</button>
    </section>

    <section>
        <h3>Listado de Profesores</h3>
        <table>
            <thead>
                <tr>
                    <th>Nombres</th>
                    <th>Apellidos</th>
                    <th>DNI</th>
                    <th>Materias</th>
                    <th>Documentación</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="elm in teachers" :key="elm.dni">
                    <td>{{ elm.teacherName }}</td>
                    <td>{{ elm.surname }}</td>
                    <td>{{ elm.dni }}</td>
                    <td>
                        <ul>
                            <li v-for="(item, index) in elm.subjects" :key="index">{{ item }}</li>
                        </ul>
                    </td>
                    <td v-if="elm.doc">
                        Subido
                    </td>
                    <td v-else>
                        No se subio
                    </td>
                </tr>
            </tbody>
        </table>
    </section>
</template>

<style scoped></style>