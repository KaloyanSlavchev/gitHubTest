# gitHubTest
package com.example.popravkaopit1.model;

import android.os.Parcel;
import android.os.Parcelable;

public class Zadaci implements Parcelable {//se nujdae ot construktor koito priema parcb obekta za da prochita danniteot parcela
    String zadNum, zadUsl, zadOtg;

    public Zadaci(String zadNum, String zadUsl, String zadOtg) {
        this.zadNum = zadNum;
        this.zadUsl = zadUsl;
        this.zadOtg = zadOtg;
    }

    protected Zadaci(Parcel in) {
        zadNum = in.readString();
        zadUsl = in.readString();
        zadOtg = in.readString();
    }

    public static final Creator<Zadaci> CREATOR = new Creator<Zadaci>() {// suzdavani obekti!!!
        @Override
        public Zadaci createFromParcel(Parcel in) {
            return new Zadaci(in);
        }

        @Override
        public Zadaci[] newArray(int size) {
            return new Zadaci[size];
        }
    };

    @Override
    public int describeContents() {
        return 0;
    }

    @Override
    public void writeToParcel(Parcel dest, int flags) { //zapisvat se obekti v tozi potok ot danni
        dest.writeString(zadNum);
        dest.writeString(zadUsl);
        dest.writeString(zadOtg);
    }

    public String getZadNum() {
        return zadNum;
    } // da se izvlichat obekti

    public String getZadUsl() {
        return zadUsl;
    }

    public String getZadOtg() {
        return zadOtg;
    }
}
